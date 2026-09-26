# Daily fare check: instructions

A scheduled Claude routine follows these steps once a day. A person can run them by hand too.

## 0. Stop conditions
- If today is on or after **2026-11-17**, or `BOOKED.md` exists in this folder, do nothing except say tracking has ended.

## 1. Searches (Apify actor `kaix/google-flights-scraper`)

Run **two** actor calls, one per cabin: `"cabinClass": "business"` and `"cabinClass": "premium-economy"`.
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
`fields: "origin,destination,departureDate,returnDate,cabinClass,price,airlines,outbound.stops,return.stops"`.
Use `outbound`/`return` segment detail only for the few rows you report on.
`price` is the **total for 3 adults**.

## 2. Filter
- Keep only rows with `outbound.stops <= 1` and (`return.stops <= 1` or no return).
- Drop exact duplicates (same route, dates, airlines, price).
- For each (cabin, trip, route, depart, return) keep the **3 cheapest** rows.

## 3. Record
Append the kept rows to `fares.csv` using its existing columns. Set `checked` to today (YYYY-MM-DD, America/New_York), `per_person_usd = round(total/3)`, and put a short note in `notes`: the carrier's connection city, "nonstop", or "recliner" for Icelandair Saga. Add TAP premium-economy rows with the note "verify cabin".

## 4. Summarize
Overwrite `LATEST.md` with:
- the check date,
- the best business fare and best premium-economy fare for each route/date combo (a short table),
- the change vs the most recent previous check of the same (cabin, trip, route, depart, return, airlines), with ▲/▼ and dollars,
- a **🔔 Alerts** section listing any of:
  - a business round trip with lie-flat seats (not Icelandair) at or under **$10,000 total**,
  - any premium-economy round trip that is not TAP at or under **$5,000 total**,
  - any fare that dropped **10% or more** since the last check.

## 5. Save
Commit to branch `claude/boston-italy-flights-bvgcsu` with the message `Daily fare check YYYY-MM-DD`, then push.

## 6. Report
End the run with a 3–5 line summary: today's best business and best premium-economy fare, the biggest move, and any alerts.
Budget: about $0.02 of Apify usage per run.
