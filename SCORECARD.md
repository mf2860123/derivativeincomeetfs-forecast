# Scorecard

Updated 2026-11-26 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**166** forecasts settled · **146** scored · **20** void (the answer was already public when it was made, so it does not count) · **233** still open · 4 duplicates not counted (the same payout forecast twice, or under a fund's old ticker)

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 137 | 72% | 21% |
| Last 30 days | 137 | 72% | 21% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 50 | 66% | 39% |
| GraniteShares | 37 | 84% | 4% |
| YieldMax | 23 | 87% | 7% |
| REX | 8 | 75% | 15% |
| NEOS | 6 | 33% | 7% |
| Defiance | 4 | 25% | 5% |
| Kurv | 4 | 50% | 10% |
| Grayscale | 3 | 33% | 131% |
| Global X | 2 | 100% | 8% |

| Model | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| range-prov-v1 | 50 | 66% | 38% |
| range-v1 | 30 | 70% | 11% |
| range-v2 | 4 | 100% | 6% |
| range-v3 (current) | 53 | 75% | 13% |

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
| 2026-11-26 | SEMY | $0.1285–$0.1389 | $0.125 below |
| 2026-11-26 | PLYY | $0.078–$0.0837 | $0.078 below |
| 2026-11-25 | HMYY | $0.0688–$0.0736 | $0.068 below |
| 2026-11-25 | COYY | $0.1167–$0.1302 | $0.083 below |
| 2026-11-24 | UNHW | $0.151–$0.3307 | $0.3815 above |
| 2026-11-23 | GDXW | $0.2342–$0.6627 | $0.2081 below |
| 2026-11-22 | AVGW | $0.0802–$0.1698 | $0.3806 above |
| 2026-11-22 | ARMW | $0.0724–$0.2311 | $0.4674 above |
| 2026-11-22 | AMDW | $0.2412–$0.645 | $1.3165 above |
| 2026-11-20 | MAGY | $0.1248–$0.1868 | $0.1903 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
