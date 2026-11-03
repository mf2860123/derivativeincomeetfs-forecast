# Forecast log: daily seals

Every forecast is written once, before its answer exists, and never edited.
After each New York trading day, that day's forecasts are sealed: each record's
SHA-256 goes into a manifest, and the manifest's own SHA-256 is the day's root.
The manifest is committed here the same day.

## Check a day

1. Find the day in `roots.csv`.
2. Hash its manifest. The result must equal the root:

       shasum -a 256 manifests/2026/2026-10-29.txt

3. Each line of a manifest is a forecast id and the SHA-256 of that forecast's
   stored record. Once a forecast has settled and its record is published,
   hash the record: it must match its line.

The time of each commit is GitHub's own record of when the seal was pushed.
An independent copy of every push event is kept by GH Archive (gharchive.org).
