# Scorecard

Updated 2026-11-14 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**96** forecasts settled · **76** scored · **20** void (the answer was already public when it was made, so it does not count) · **221** still open · 4 duplicates not counted (the same payout forecast twice, or under a fund's old ticker)

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 68 | 74% | 29% |
| Last 30 days | 68 | 74% | 29% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 31 | 65% | 45% |
| GraniteShares | 14 | 93% | 2% |
| YieldMax | 8 | 100% | 5% |
| NEOS | 3 | 33% | 2% |
| Defiance | 3 | 33% | 4% |
| REX | 3 | 100% | 19% |
| Grayscale | 3 | 33% | 131% |
| Global X | 2 | 100% | 8% |
| Kurv | 1 | 100% | 0% |

| Model | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| range-prov-v1 | 20 | 60% | 67% |
| range-v1 | 25 | 76% | 11% |
| range-v2 | 3 | 100% | 6% |
| range-v3 (current) | 20 | 80% | 16% |

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
| 2026-11-14 | TSLW | $0.1016–$0.3322 | $0.0706 below |
| 2026-11-14 | NFLW | $0.0213–$0.0852 | $0.1021 above |
| 2026-11-14 | BBYY | $0.0605–$0.0658 | $0.06 below |
| 2026-11-14 | AVGW | $0.1802–$0.3659 | $0.125 below |
| 2026-11-14 | METW | $0.092–$0.1683 | $0.1791 above |
| 2026-11-14 | GOOW | $0.0563–$0.1176 | $0.3538 above |
| 2026-11-14 | GLDW | $0.0789–$0.2006 | $0.2236 above |
| 2026-11-14 | UBEW | $0.0868–$0.1922 | $0.2054 above |
| 2026-11-14 | ARMW | $0.1787–$0.5175 | $0.1517 below |
| 2026-11-14 | AMZW | $0.0836–$0.2464 | $0.3268 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
