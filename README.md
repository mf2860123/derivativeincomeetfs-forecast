# Forecast seals

Public, tamper-evident proof of every forecast published by
[derivativeincomeetfs.com](https://derivativeincomeetfs.com).

Each forecast is written once, before its answer exists, and never edited.
After every New York trading day, that day's forecasts are sealed and the seal
is committed to this repository. Anyone can check that a forecast existed
before the payout it predicted was announced.

## What is in here

| Path | What it holds |
| --- | --- |
| `manifests/YYYY/YYYY-MM-DD.txt` | One line per forecast made that day: the forecast id and the SHA-256 of its stored record |
| `roots.csv` | One row per sealed day: the date, the number of forecasts and the day's root hash (the SHA-256 of that day's manifest) |

The manifests contain hashes only. The forecasts themselves stay private until
they settle, so nothing can be copied or traded on before the answer is known.
Settled records are published with the track record, and each one must hash to
its line here.

## What we forecast

| Forecast | What it predicts | Scored against |
| --- | --- | --- |
| Payout range | The next distribution of a fund: a middle value and an 80% range | "Same as last time" (the last payout) |
| Cut warning | The chance the next YieldMax distribution is more than 20% below the last | The 11.7% historical base rate |

Both are issued automatically after each payout, by rules fixed in advance:

- **Payout range:** the range comes from the fund's own recent forecast misses. It should catch the real payout about 8 times in 10, and the score shows whether it does.
- **Cut warning:** compares the latest payout with the median of the fund's previous eight. Payouts well above their own average are followed by cuts far more often than normal (from a study of 2,800 YieldMax distributions in the funds' Section 19(a) notices).

A forecast is **void** (kept in the log but not scored) if its answer was public
before it was made, or if the fund changed its payment schedule (for example
monthly to weekly) before the next payout. Misses are never removed.

## Check a day yourself

1. Find the day in `roots.csv`.
2. Hash that day's manifest. The result must equal the root:

   macOS / Linux:

       shasum -a 256 manifests/2026/2026-11-04.txt

   Windows (PowerShell):

       Get-FileHash manifests\2026\2026-11-04.txt -Algorithm SHA256

   Any system with Python:

       python3 -c "import hashlib,sys;print(hashlib.sha256(open(sys.argv[1],'rb').read()).hexdigest())" manifests/2026/2026-11-04.txt

3. Once a forecast has settled and its record is published, hash the record the
   same way. It must match the forecast's line in the manifest.

## Why this proves timing

- The commit time is GitHub's own record of when each seal was pushed.
- An independent copy of every public push is kept by [GH Archive](https://www.gharchive.org/).
- The day's root hash is also posted on X ([@highdividendetf](https://x.com/highdividendetf)).

Changing any forecast after the fact would change its hash, which would change
the manifest's hash, which would no longer match the root that was already
committed and posted.

## Track record and research

Settled forecasts, scores, calibration and the research behind each model are at
**[derivativeincomeetfs.com](https://derivativeincomeetfs.com)**.

## Not advice

Forecasts are probabilities and estimates, not investment advice or a promise of
any outcome. Past accuracy does not guarantee future accuracy.
