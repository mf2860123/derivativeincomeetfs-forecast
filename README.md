# Forecast log: daily seals

**Scorecard (updated 2026-11-12):** 25 payout forecasts settled, 76% inside their 80% range (an honest range should catch about 80%). Full results, misses included: [SCORECARD.md](SCORECARD.md)

Every forecast is written once, before its answer exists, and never edited.
After each New York trading day, that day's forecasts are sealed: each record's
SHA-256 goes into a manifest, and the manifest's own SHA-256 is the day's root.
The manifest is committed here the same day.

## Check a day

1. Find the day in `roots.csv`.
2. Hash its manifest. The result must equal the root:

       shasum -a 256 manifests/2026/2026-10-29.txt

3. Each line of a manifest is a forecast id and the SHA-256 of that forecast's
   stored record. Full records go to subscribers; anyone checking a specific
   claim can ask for the record, hash it, and it must match its line.

The time of each commit is GitHub's own record of when the seal was pushed.
An independent copy of every push event is kept by GH Archive (gharchive.org).
