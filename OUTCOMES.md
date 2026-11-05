# Outcomes

Forecasts are sealed the day they are made (`manifests/`, `roots.csv`). When a forecast
settles, or is voided, it is sealed again with its outcome:

| Path | What it holds |
| --- | --- |
| `outcomes/YYYY/YYYY-MM-DD.txt` | One line per forecast settled that day: id, `resolved` or `void`, SHA-256 of the outcome record, SHA-256 of the forecast record |
| `outcome-roots.csv` | One row per day: date, settled, voided, root (the SHA-256 of that day's outcomes file) |

The forecast and outcome records themselves go to subscribers. Anyone checking a specific
claim can ask for the two records of that forecast.

## Check a forecast end to end

1. Hash the forecast record. It must match the forecast's line in the manifest of the day
   it was made (`manifests/`), which was committed before the answer existed.
2. Hash the outcome record. It must match its line in `outcomes/`.
3. Check the actual payout in the outcome against the fund issuer's own page or notice.

Voids are listed like every other outcome, each with its reason (the payout was public
before the forecast, or the fund changed its payment schedule). Nothing settled is left out.
