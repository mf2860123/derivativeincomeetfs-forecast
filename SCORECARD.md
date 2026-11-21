# Scorecard

Updated 2026-11-21 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**142** forecasts settled · **122** scored · **20** void (the answer was already public when it was made, so it does not count) · **226** still open · 4 duplicates not counted (the same payout forecast twice, or under a fund's old ticker)

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 113 | 73% | 21% |
| Last 30 days | 113 | 73% | 21% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 39 | 69% | 37% |
| GraniteShares | 24 | 92% | 2% |
| YieldMax | 23 | 87% | 7% |
| REX | 8 | 75% | 15% |
| NEOS | 6 | 33% | 7% |
| Defiance | 4 | 25% | 5% |
| Kurv | 4 | 50% | 10% |
| Grayscale | 3 | 33% | 131% |
| Global X | 2 | 100% | 8% |

| Model | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| range-prov-v1 | 40 | 65% | 38% |
| range-v1 | 30 | 70% | 11% |
| range-v2 | 4 | 100% | 6% |
| range-v3 (current) | 39 | 82% | 12% |

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
| 2026-11-20 | MAGY | $0.1248–$0.1868 | $0.1903 above |
| 2026-11-19 | BTCI | $0.5897–$0.7807 | $0.5481 below |
| 2026-11-19 | QQQI | $0.6125–$0.6546 | $0.5838 below |
| 2026-11-18 | QLDY | $0.1401–$0.1488 | $0.1331 below |
| 2026-11-17 | KYLD | $0.097–$0.103 | $0.08 below |
| 2026-11-17 | AAPY | $0.25–$0.25 | $0.3 above |
| 2026-11-17 | YMAX | $0.0238–$0.0291 | $0.0386 above |
| 2026-11-17 | NVIT | $0.1838–$0.2246 | $0.1774 below |
| 2026-11-17 | MSST | $0.1141–$0.1395 | $0.1102 below |
| 2026-11-17 | TSII | $0.0863–$0.1437 | $0.1579 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
