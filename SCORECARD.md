# Scorecard

Updated 2026-11-08 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**16** forecasts settled · **14** scored · **2** void (the answer was already public when it was made, so it does not count) · **33** still open

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 13 | 69% | 15% |
| Last 30 days | 13 | 69% | 15% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 7 | 71% | 23% |
| Defiance | 3 | 33% | 4% |
| Global X | 2 | 100% | 8% |
| YieldMax | 1 | 100% | 7% |

## Cut warnings

Each gives the probability that a fund's next payout is cut by more than 20%. Scored by Brier score (lower is better) against simply using the historical cut rate.

| | Forecasts | Brier | vs the historical cut rate | Warned (≥12%) | Of those, cut | Cut rate overall |
| --- | --- | --- | --- | --- | --- | --- |
| All time | 1 | 0.003 | 78% better | 0 | – | 0% |
| Last 30 days | 1 | 0.003 | 78% better | 0 | – | 0% |

## Latest misses

| Settled | Fund | Forecast range | Actual |
| --- | --- | --- | --- |
| 2026-11-06 | UNHW | $0.2571–$0.5313 | $0.2342 below |
| 2026-11-05 | WDTE | $0.1595–$0.1646 | $0.1586 below |
| 2026-11-05 | QQQY | $0.1188–$0.1288 | $0.1172 below |
| 2026-11-04 | RDTE | $0.0483–$0.1197 | $0.123 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
