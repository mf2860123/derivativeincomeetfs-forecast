# Scorecard

Updated 2026-11-04 (New York). Every number below comes from records published in `records/`, each sealed by its hash before the answer was known.

**5** forecasts settled · **5** scored · **0** void (the answer was already public when it was made, so it does not count) · **42** still open

## Payout ranges

Each forecast gives an 80% range for a fund's next payout. If the ranges are honest, about 80% of payouts land inside them.

| | Forecasts | Inside the range | Average error | Naive baseline error | Error vs baseline | Average % error |
| --- | --- | --- | --- | --- | --- | --- |
| All time | 5 | 80% | $0.0189 | $0.0189 | the same | 15% |
| Last 30 days | 5 | 80% | $0.0189 | $0.0189 | the same | 15% |

The naive baseline assumes the next payout equals the last one.

| Issuer | Forecasts | Inside the range | Error vs baseline |
| --- | --- | --- | --- |
| Roundhill | 3 | 67% | the same |
| Global X | 2 | 100% | the same |

## Latest misses

| Settled | Fund | Forecast range | Actual | Record |
| --- | --- | --- | --- | --- |
| 2026-11-04 | RDTE | $0.0483–$0.1197 | $0.123 above | [forecast](records/2026/2026-11-03-dist-RDTE-c05bb9.json) · [result](records/2026/2026-11-03-dist-RDTE-c05bb9.result.json) |

Records appear here after the day's outcome seal, so the newest links can take a day to work.

## Check any number yourself

Every row above is a record in `records/`. Hash a record (`shasum -a 256 records/2026/<id>.json`) and find that hash in the manifest of the day the forecast was made (`manifests/`). That manifest was committed here before the payout was announced. See [README.md](README.md) and [OUTCOMES.md](OUTCOMES.md).
