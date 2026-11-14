# Scorecard

Updated 2026-11-13 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**64** forecasts settled · **45** scored · **19** void (the answer was already public when it was made, so it does not count) · **207** still open · 4 duplicates not counted (the same payout forecast twice, or under a fund's old ticker)

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 37 | 73% | 26% |
| Last 30 days | 37 | 73% | 26% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 14 | 71% | 31% |
| YieldMax | 8 | 100% | 5% |
| NEOS | 3 | 33% | 2% |
| Defiance | 3 | 33% | 4% |
| REX | 3 | 100% | 19% |
| Grayscale | 3 | 33% | 131% |
| Global X | 2 | 100% | 8% |
| Kurv | 1 | 100% | 0% |

| Model | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| range-prov-v1 | 7 | 57% | 83% |
| range-v1 | 25 | 76% | 11% |
| range-v2 | 3 | 100% | 6% |
| range-v3 (current) | 2 | 50% | 41% |

## Cut warnings

Each gives the probability that a fund's next payout is cut by more than 20%. Scored by Brier score (lower is better) against simply using the historical cut rate.

| | Forecasts | Brier | vs the historical cut rate | Warned (≥12%) | Of those, cut | Cut rate overall |
| --- | --- | --- | --- | --- | --- | --- |
| All time | 8 | 0.005 | too few to judge | 1 | 0% | 0% |
| Last 30 days | 8 | 0.005 | too few to judge | 1 | 0% | 0% |

Too few to judge yet: 8 warnings settled and 0 cuts among them. The comparison with the historical cut rate is shown once 30 have settled and at least one fund has been cut.

## Latest misses

| Settled | Fund | Forecast range | Actual |
| --- | --- | --- | --- |
| 2026-11-14 | ARMW | $0.1787–$0.5175 | $0.1517 below |
| 2026-11-14 | AMZW | $0.0836–$0.2464 | $0.3268 above |
| 2026-11-13 | BTCC | $0.1715–$0.248 | $0.14 below |
| 2026-11-13 | BPI | $0.0961–$0.352 | $0.045 below |
| 2026-11-10 | BNDI | $0.2123–$0.2194 | $0.2196 above |
| 2026-11-10 | TLTI | $0.2062–$0.22 | $0.2251 above |
| 2026-11-06 | UNHW | $0.2571–$0.5313 | $0.2342 below |
| 2026-11-05 | WDTE | $0.1595–$0.1646 | $0.1586 below |
| 2026-11-05 | QQQY | $0.1188–$0.1288 | $0.1172 below |
| 2026-11-04 | RDTE | $0.0483–$0.1197 | $0.123 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
