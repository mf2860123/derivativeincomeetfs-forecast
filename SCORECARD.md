# Scorecard

Updated 2026-11-17 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**133** forecasts settled · **113** scored · **20** void (the answer was already public when it was made, so it does not count) · **222** still open · 4 duplicates not counted (the same payout forecast twice, or under a fund's old ticker)

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 104 | 75% | 21% |
| Last 30 days | 104 | 75% | 21% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 35 | 69% | 40% |
| GraniteShares | 24 | 92% | 2% |
| YieldMax | 23 | 87% | 7% |
| REX | 7 | 71% | 16% |
| Kurv | 4 | 50% | 10% |
| NEOS | 3 | 33% | 2% |
| Defiance | 3 | 33% | 4% |
| Grayscale | 3 | 33% | 131% |
| Global X | 2 | 100% | 8% |

| Model | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| range-prov-v1 | 39 | 67% | 39% |
| range-v1 | 27 | 74% | 11% |
| range-v2 | 4 | 100% | 6% |
| range-v3 (current) | 34 | 82% | 11% |

## Cut warnings

Each gives the probability that a fund's next payout is cut by more than 20%. Scored by Brier score (lower is better) against simply using the historical cut rate.

| | Forecasts | Brier | vs the historical cut rate | Warned (≥12%) | Of those, cut | Cut rate overall |
| --- | --- | --- | --- | --- | --- | --- |
| All time | 9 | 0.004 | too few to judge | 1 | 0% | 0% |
| Last 30 days | 9 | 0.004 | too few to judge | 1 | 0% | 0% |

Too few to judge yet: 9 warnings settled and 0 cuts among them. The comparison with the historical cut rate is shown once 30 have settled and at least one fund has been cut.

## Latest misses

| Settled | Fund | Forecast range | Actual |
| --- | --- | --- | --- |
| 2026-11-17 | KYLD | $0.097–$0.103 | $0.08 below |
| 2026-11-17 | AAPY | $0.25–$0.25 | $0.3 above |
| 2026-11-17 | YMAX | $0.0238–$0.0291 | $0.0386 above |
| 2026-11-17 | NVIT | $0.1838–$0.2246 | $0.1774 below |
| 2026-11-17 | MSST | $0.1141–$0.1395 | $0.1102 below |
| 2026-11-17 | TSII | $0.0863–$0.1437 | $0.1579 above |
| 2026-11-17 | ATCL | $0.2728–$0.2896 | $0.2673 below |
| 2026-11-14 | COYY | $0.1357–$0.15 | $0.131 below |
| 2026-11-14 | TSLW | $0.1016–$0.3322 | $0.0706 below |
| 2026-11-14 | NFLW | $0.0213–$0.0852 | $0.1021 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
