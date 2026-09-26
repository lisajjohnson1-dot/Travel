# Italy, November 2026: Flight Tracker

**Travelers:** 3 adults · **From:** Boston (BOS)
**Out:** Wed Nov 18 or Thu Nov 19 · **Home:** Sun Nov 29 or Mon Nov 30
**Budget:** **under $4,000 total for all 3** (about $1,333 per person)
**Cabins tracked:** economy, plus premium economy / extra legroom when it fits the budget
**Stops:** nonstop or 1 stop each way (2+ stops are filtered out)
**Daily check:** automatic, see [`TRACKING.md`](TRACKING.md) · Today's best: [`LATEST.md`](LATEST.md)

Full price history: [`fares.csv`](fares.csv). All prices are Google Flights totals **for 3 adults** in USD.

---

## Trip shape, with Pompeii

| Dates | Plan |
|---|---|
| Wed Nov 18 | Overnight flight out of Boston |
| Thu Nov 19 – Sun Nov 22 | **Pompeii (and Rome or Naples).** Rome → Naples is about 1h10 on the fast train; Naples → Pompeii is about 40 min on the Circumvesuviana. Florence → Naples is about 3h. |
| Sun Nov 22 | Train to Florence |
| Mon Nov 23 – Thu Nov 26 AM | Florence |
| Thu Nov 26 PM – Sat Nov 28 | Tuscany: Siena, Chianti, Montalcino, Montepulciano |
| Sat Nov 28 / Sun Nov 29 | Back to Florence |
| Sun Nov 29 or Mon Nov 30 | Fly home |

---

## Best fares within budget (checked 2026-09-26, economy, 3 adults)

| Option | Dates | Total for 3 | Per person | Why / catch |
|---|---|---|---|---|
| ⭐ **SWISS Boston ⇄ Florence** | Nov 18 → Nov 30 | **$2,956** | $985 | **Best overall.** Short 85-min Zurich connections both ways. Lands Florence 1:50pm Nov 19; home lands Boston 8:20pm Nov 30. Leaves about $1,000 in the budget for extra-legroom seats or bags. |
| **SWISS / Lufthansa Boston ⇄ Florence** | Nov 18 → Nov 30 | $2,978 | $993 | Same outbound; home via Munich, lands Boston 6:35pm |
| **TAP Boston ⇄ Rome** | Nov 18 → Nov 30 | $2,543 | $848 | Via Lisbon both ways (about 2h connections). Lands Rome 11:25am Nov 19, so the Pompeii days start from Rome. |
| Cheapest | TAP Boston ⇄ Rome, Nov 18 → Nov 30 | $1,904 | $635 | Overnight layover in Lisbon on the way home |
| Cheapest into Florence | SWISS / Austrian, Nov 18 → Nov 30 | $2,383 | $794 | Overnight layover in Vienna on the way home |

**Coming home Nov 29 costs more than Nov 30.** It's the Sunday after Thanksgiving: SWISS Nov 18 → 29 with good connections is $3,829.

### Premium economy / extra legroom

- A real premium economy round trip on SWISS, Delta, ITA or BA **does not fit $4,000 right now**. Delta's nonstop to Rome alone is $3,650 one-way for 3. The daily check will flag it if one drops under budget.
- TAP shows "premium economy" around $2,600 for 3, but TAP has no true premium economy cabin on these planes. It's likely an extra-legroom economy seat.
- **Cheaper route to legroom:** book the SWISS or TAP economy fare, then pay for extra-legroom or exit-row seats on the long flights. The SWISS fare leaves room in the budget for that. Check the price in the seat map before paying.

### Nonstop option

Delta's nonstop to Rome is $1,370 for 3 one-way (DL112, Nov 18). The nonstops home (Delta or ITA, Nov 29) are about $2,770–2,880 as one-ways, which makes the pair about $4,100–4,300, just over budget. On a single ticket the pair may come in lower, so use the link below.

---

## Check live prices (click to open Google Flights)

- [Economy, BOS⇄FLR Nov 18 → Nov 30, 3 adults](https://www.google.com/travel/flights?q=Flights%20for%203%20adults%20from%20BOS%20to%20FLR%20on%202026-11-18%20returning%202026-11-30)
- [Economy, BOS⇄FCO Nov 18 → Nov 30, 3 adults](https://www.google.com/travel/flights?q=Flights%20for%203%20adults%20from%20BOS%20to%20FCO%20on%202026-11-18%20returning%202026-11-30)
- [Economy, nonstop BOS⇄FCO Nov 18 → Nov 29, 3 adults](https://www.google.com/travel/flights?q=Nonstop%20flights%20for%203%20adults%20from%20BOS%20to%20FCO%20on%202026-11-18%20returning%202026-11-29)
- [Premium economy, BOS⇄FCO Nov 18 → Nov 30, 3 adults](https://www.google.com/travel/flights?q=Premium%20economy%20flights%20for%203%20adults%20from%20BOS%20to%20FCO%20on%202026-11-18%20returning%202026-11-30)

On each Google Flights page, switch on **Track prices** to get emails when the fare moves.

## How this tracker works

- A scheduled Claude routine runs every morning at 6:52am Boston time. It re-runs the searches in [`TRACKING.md`](TRACKING.md) (economy and premium economy, 3 adults, all four date combos, max 1 stop each way), appends new rows to `fares.csv`, rewrites [`LATEST.md`](LATEST.md), and flags budget fares and price drops.
- `fares.csv` holds one row per fare observation, dated by the `checked` column, so price movement stays visible over time.
- Round-trip rows show the cheapest outbound combined with return options. Use the links above to see other combinations.

## Things to know

- **Thanksgiving is Thu Nov 26.** Fares home on Sun Nov 29 run noticeably higher than Mon Nov 30.
- Prices include standard taxes. Basic or "light" fares may charge for checked bags and seat selection, so budget roughly $100–200 per person for bags if you check them.
- November is low season in Italy, but transatlantic fares for Thanksgiving week usually rise as the date gets close. **A good fare under budget is worth booking** rather than waiting for a last-minute drop.
