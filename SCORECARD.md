# Scorecard

Updated 2026-11-04 (New York). Every forecast counted here was sealed by its hash before the payout was announced.

**5** forecasts settled · **5** scored · **0** void (the answer was already public when it was made, so it does not count) · **42** still open

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| All time | 5 | 80% | 15% |
| Last 30 days | 5 | 80% | 15% |

| Issuer | Forecasts | Inside the range | Average error |
| --- | --- | --- | --- |
| Roundhill | 3 | 67% | 20% |
| Global X | 2 | 100% | 8% |

## Latest misses

| Settled | Fund | Forecast range | Actual |
| --- | --- | --- | --- |
| 2026-11-04 | RDTE | $0.0483–$0.1197 | $0.123 above |

## Check it yourself

Each forecast's SHA-256 is in the manifest of the day it was made (`manifests/`), committed here that day, before the payout was announced; its outcome is sealed the same way (`outcomes/`). Full records go to subscribers. To check any forecast, ask for its record, hash it (`shasum -a 256 <id>.json`) and find the hash in that day's manifest. See [README.md](README.md).
