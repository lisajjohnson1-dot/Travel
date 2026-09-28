# Daily fare check: instructions

A scheduled Claude routine follows these steps once a day. A person can run them by hand too.

**Budget: under $4,000 total for 3 adults.** Business class is out of scope. Don't search it.

## 0. Stop conditions
- If today is on or after **2026-11-17**, or `BOOKED.md` exists in this folder, do nothing except say tracking has ended.

## 1. Searches (Apify actor `kaix/google-flights-scraper`)

Run **two** actor calls, one per cabin: `"cabinClass": "economy"` and `"cabinClass": "premium-economy"`.
Common input: `"adults": 3, "currency": "USD", "maxResults": 8`.
Do **not** pass `maxStops` or `airlines`. Those filters make Google return an error; filter afterwards instead (step 2).

`searches` (the same 12 for both cabins):

| # | origin | destination | departureDate | returnDate |
|---|---|---|---|---|
| 1–4 | BOS | FCO | 2026-11-18 / 2026-11-19 | 2026-11-29 / 2026-11-30 (all 4 combos) |
| 5–8 | BOS | FLR | 2026-11-18 / 2026-11-19 | 2026-11-29 / 2026-11-30 (all 4 combos) |
| 9 | BOS | FCO | 2026-11-18 | none (one-way) |
| 10 | FLR | BOS | 2026-11-30 | none (one-way) |
| 11 | FCO | BOS | 2026-11-29 | none (one-way) |
| 12 | FLR | BOS | 2026-11-29 | none (one-way) |

Start both calls with `waitSecs: 0`, then poll `get-actor-run` until SUCCEEDED (about 3 minutes). Read results with `get-dataset-items`, using
`fields: "origin,destination,departureDate,returnDate,cabinClass,price,totalDuration,airlines,outbound.stops,return.stops"`.
Use `outbound`/`return` segment detail only for the few rows you report on (connection city, arrival times, and whether any layover is overnight).
`price` is the **total for 3 adults**.

## 2. Filter
- Keep only rows with `outbound.stops <= 1` and (`return.stops <= 1` or no return).
- Drop exact duplicates (same route, dates, airlines, price).
- For each (cabin, trip, route, depart, return) keep the **3 cheapest** rows.

## 3. Record
Append the kept rows to `fares.csv` using its existing columns. Set `checked` to today (YYYY-MM-DD, America/New_York) and `per_person_usd = round(total/3)`. Put a short note in `notes`, such as the connection city, "nonstop", or "overnight layover". Add TAP premium-economy rows with the note "verify cabin".

## 4. Summarize
Overwrite `LATEST.md` with:
- the check date and the budget line,
- a short table of the best round trips (economy and premium economy), with total, per person, and ✅/❌ for under $4,000,
- the change vs the most recent previous check of the same (cabin, trip, route, depart, return, airlines), with ▲/▼ and dollars,
- a **🔔 Alerts** section listing any of:
  - a **premium-economy round trip (not TAP)** at or under **$4,000 total**,
  - a round trip with a **nonstop on both legs** at or under **$4,000 total**,
  - any economy round trip with short connections (no overnight layover) at or under **$2,500 total**,
  - the SWISS BOS⇄FLR Nov 18 → Nov 30 fare (baseline $2,956) or the TAP BOS⇄FCO Nov 18 → Nov 30 fare with 2h connections (baseline $2,543) moving by **$150 or more** in either direction,
  - the cheapest in-budget fare with short connections rising above **$3,500** (fares are climbing, so book soon).

## 5. Save
Commit to branch `claude/boston-italy-flights-bvgcsu` with the message `Daily fare check YYYY-MM-DD`, then push.

## 6. Report
End the run with a 3–5 line summary: the best in-budget fare today (airline, dates, total for 3), the best premium-economy fare, the biggest move, and any alerts.
Budget: about $0.02 of Apify usage per run.
