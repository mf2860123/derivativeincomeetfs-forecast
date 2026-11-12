# Scorecard

Updated 2026-11-12 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**41** forecasts settled · **33** scored · **8** void (the answer was already public when it was made, so it does not count) · **222** still open · 4 duplicates not counted (the same payout forecast twice, or under a fund's old ticker)

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 26 | 77% | 11% |
| Last 30 days | 26 | 77% | 11% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 8 | 75% | 20% |
| YieldMax | 6 | 100% | 4% |
| NEOS | 3 | 33% | 2% |
| Defiance | 3 | 33% | 4% |
| REX | 3 | 100% | 19% |
| Global X | 2 | 100% | 8% |
| Kurv | 1 | 100% | 0% |

| Model | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| range-v1 | 25 | 76% | 11% |
| range-v2 | 1 | 100% | 3% |

## Cut warnings

Each gives the probability that a fund's next payout is cut by more than 20%. Scored by Brier score (lower is better) against simply using the historical cut rate.

| | Forecasts | Brier | vs the historical cut rate | Warned (≥12%) | Of those, cut | Cut rate overall |
| --- | --- | --- | --- | --- | --- | --- |
| All time | 7 | 0.005 | too few to judge | 1 | 0% | 0% |
| Last 30 days | 7 | 0.005 | too few to judge | 1 | 0% | 0% |

Too few to judge yet: 7 warnings settled and 0 cuts among them. The comparison with the historical cut rate is shown once 30 have settled and at least one fund has been cut.

## Latest misses

| Settled | Fund | Forecast range | Actual |
| --- | --- | --- | --- |
| 2026-11-10 | BNDI | $0.2123–$0.2194 | $0.2196 above |
| 2026-11-10 | TLTI | $0.2062–$0.22 | $0.2251 above |
| 2026-11-06 | UNHW | $0.2571–$0.5313 | $0.2342 below |
| 2026-11-05 | WDTE | $0.1595–$0.1646 | $0.1586 below |
| 2026-11-05 | QQQY | $0.1188–$0.1288 | $0.1172 below |
| 2026-11-04 | RDTE | $0.0483–$0.1197 | $0.123 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
