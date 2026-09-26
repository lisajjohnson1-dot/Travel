# Italy, November 2026: Flight Tracker

**Travelers:** 3 adults · **From:** Boston (BOS)
**Out:** Wed Nov 18 or Thu Nov 19 · **Home:** Sun Nov 29 or Mon Nov 30
**Cabins tracked:** business and premium economy (extra legroom); economy for reference only

Full price history: [`fares.csv`](fares.csv). All prices are Google Flights totals **for 3 adults** in USD, checked 2026-09-26.

---

## Trip shape, with Pompeii

| Dates | Plan |
|---|---|
| Wed Nov 18 | Overnight flight out of Boston |
| Thu Nov 19 – Sun Nov 22 | **Rome and Pompeii.** Rome → Naples is about 1h10 on the fast train; the Circumvesuviana or a driver covers Naples → Pompeii (about 40 min). A night in Naples or Sorrento makes it an easy day. |
| Sun Nov 22 | Fast train to Florence (Naples → Florence about 3h, Rome → Florence about 1h35) |
| Mon Nov 23 – Thu Nov 26 AM | Florence |
| Thu Nov 26 PM – Sat Nov 28 | Tuscany: Siena, Chianti, Montalcino, Montepulciano |
| Sat Nov 28 / Sun Nov 29 | Back to Florence |
| Sun Nov 29 or Mon Nov 30 | Fly home from **Florence (FLR)**, or take the train to Rome (FCO) for a nonstop |

The four free days before Florence are where Pompeii fits. The best ticket shape is **open-jaw**: into Rome, home from Florence. If you'd rather land in Florence, SWISS gets you to FLR by 1:50pm Nov 19. From there Pompeii is a 3-hour train south and back to Florence by Sunday.

---

## Business class, best options (3 adults)

| Option | Route / dates | Total for 3 | Per person | Notes |
|---|---|---|---|---|
| ⭐ **Most comfortable into Florence** | SWISS BOS⇄FLR, Nov 18 → Nov 30 | **$14,260** | $4,753 | LX53 overnight via Zurich (85 min) with a lie-flat seat. Home on LX1675 + LX52, landing BOS 8:20pm. |
| ⭐ **Nonstop into Rome** | ITA AZ615 BOS→FCO Nov 18 (nonstop, 5:20pm → 7:15am) | $12,977 one-way | $4,326 | Also nonstop home: AZ614 FCO→BOS Nov 29, $12,062. These are one-way prices. **A round trip or open-jaw on one ticket is usually much cheaper**, so check the link below. |
| **Cheapest business** | Icelandair BOS⇄FCO, Nov 18 → Nov 30 | **$9,627** | $3,209 | Via Reykjavik. Saga Premium is a large recliner, **not lie-flat**. |
| Budget business into Florence | SWISS out, Air Dolomiti + Air Canada home, Nov 18 → Nov 29/30 | $10,446 | $3,482 | Lie-flat outbound. The return leaves FLR at 6:30am and connects in Frankfurt and Montreal. |

Other business one-ways found: BA via London (BOS→FCO $10,245; FLR→BOS $12,139), Air France via Paris ($12,787), Delta nonstop FCO→BOS ($18,257).

## Premium economy / extra legroom, best options (3 adults)

| Option | Route / dates | Total for 3 | Per person | Notes |
|---|---|---|---|---|
| ⭐ **Nonstop out** | Delta DL112 BOS→FCO Nov 18 (6:45pm → 8:45am) | $3,650 one-way | $1,217 | Delta Premium Select |
| ⭐ **Nonstop out** | ITA AZ615 BOS→FCO Nov 18 (5:20pm → 7:15am) | $3,932 one-way | $1,311 | |
| Home via London | BA FLR→BOS Nov 30 | $6,027 one-way | $2,009 | One stop, World Traveller Plus |
| Home via London | BA FCO→BOS Nov 30 | $6,082 one-way | $2,027 | |
| Lowest price, but check the seat | TAP BOS⇄FCO or BOS⇄FLR, Nov 18 → Nov 30 | ~$2,600 | ~$865 | ⚠️ TAP has no real premium economy cabin on these planes, so this is likely an extra-legroom economy seat. The return also has an overnight layover in Lisbon. |

Premium economy home-leg prices are much higher as one-ways (Delta nonstop FCO→BOS showed $9,208). **Price the nonstop as a round trip or open-jaw**, where it should come down a lot.

## Economy (reference)

About $635–$800 per person round trip (TAP via Lisbon, SWISS/Austrian into Florence), so roughly $1,900–$2,400 for 3.

---

## Check live prices (click to open Google Flights)

- [Business, open-jaw BOS→FCO Nov 18 / FLR→BOS Nov 30, 3 adults](https://www.google.com/travel/flights?q=Business%20class%20flights%20for%203%20adults%20from%20BOS%20to%20FCO%20on%202026-11-18%20and%20from%20FLR%20to%20BOS%20on%202026-11-30)
- [Business, BOS⇄FCO nonstop Nov 18 → Nov 29, 3 adults](https://www.google.com/travel/flights?q=Nonstop%20business%20class%20flights%20for%203%20adults%20from%20BOS%20to%20FCO%20on%202026-11-18%20returning%202026-11-29)
- [Business, BOS⇄FLR Nov 18 → Nov 30, 3 adults](https://www.google.com/travel/flights?q=Business%20class%20flights%20for%203%20adults%20from%20BOS%20to%20FLR%20on%202026-11-18%20returning%202026-11-30)
- [Premium economy, BOS⇄FCO nonstop Nov 18 → Nov 29, 3 adults](https://www.google.com/travel/flights?q=Nonstop%20premium%20economy%20flights%20for%203%20adults%20from%20BOS%20to%20FCO%20on%202026-11-18%20returning%202026-11-29)
- [Premium economy, open-jaw BOS→FCO Nov 18 / FLR→BOS Nov 30, 3 adults](https://www.google.com/travel/flights?q=Premium%20economy%20flights%20for%203%20adults%20from%20BOS%20to%20FCO%20on%202026-11-18%20and%20from%20FLR%20to%20BOS%20on%202026-11-30)

On each Google Flights page, switch on **Track prices** to get emails when the fare moves.

## How this tracker works

- `fares.csv` holds one row per fare observation. New checks are appended with a new `checked` date, so price movement stays visible over time.
- Searches: BOS ⇄ FCO / FLR (plus one-ways FCO/FLR → BOS) for all four date combinations, in business and premium economy, for 3 adults.
- Data comes from Google Flights through an Apify scraper. Round-trip rows show the cheapest outbound combined with return options, so **nonstop round trips (ITA/Delta) need the links above** to see their real combined price.

## Things to know

- **Thanksgiving is Thu Nov 26.** U.S. fares for the Sunday/Monday after Thanksgiving (Nov 29/30) run high. The return leg is where you'll see the most movement.
- November is low season in Italy. The ITA and Delta nonstops from Boston both showed up for these dates (Nov 18 out, Nov 29 back).
- Suggested target: a lie-flat business fare under about **$10,000 for 3**, or a nonstop premium economy round trip under about **$5,000 for 3**, is a good price to book.
