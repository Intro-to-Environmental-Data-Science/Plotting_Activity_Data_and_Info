# Global surface temperature anomalies (monthly, two sources)

**File:** `data/global_temperature_anomaly.csv` · **Rows:** 3,871 (two series stacked) · **Coverage:** `GCAG` Jan 1850 – Jul 2026 (2,119 rows); `GISTEMP` Jan 1880 – Dec 2025 (1,752 rows)

**Source:** GitHub mirror `datasets/global-temp`, which combines NASA GISS's GISTEMP and a second series labeled "GCAG".
**License / use:** Mirror is CC BY 4.0. NASA GISTEMP is a US Government work (public domain). If the GCAG series is from the UK Met Office (see caveat below), it is under the Open Government Licence v3 and needs the Met Office acknowledgement.
**Cite as:** GISTEMP Team (2024). GISS Surface Temperature Analysis (GISTEMP), version 4. NASA GISS. data.giss.nasa.gov/gistemp/ — plus the GCAG source once confirmed.

## Variables

| Column | Description | Units |
|---|---|---|
| `source` | Which analysis: `GISTEMP` or `GCAG` | |
| `date` | First day of the month (a real date) | |
| `year`, `month` | Pulled out of `date` for convenience | |
| `anomaly_c` | Global mean temperature anomaly | °C, relative to each source's own baseline |

## Watch out for
- **The two series use different baselines.** GISTEMP is relative to 1951–1980. Over the 1880–2025 overlap, GISTEMP averages about 0.08 °C higher than GCAG, so a gap between the lines is mostly a baseline difference, not disagreement.
- **Provenance of `GCAG` is unclear.** The source repo's README describes it as NOAA's Climate at a Glance but links to the HadCRUT5 download page. Confirm before citing it.
- Monthly data are noisy; annual means show the trend more clearly.

## Changes from source
Columns renamed (the source column called `Year` actually held YYYY-MM); `date` converted to YYYY-MM-DD; `year` and `month` added; sorted by source and date.

## Ideas to try
- `geom_line()` with `color = source`, or `facet_wrap(facets = "source", nrow = 2)`.
- `filter(year >= 1980)` to zoom in on recent decades.
- `group_by(source, year)` + `summarize(mean(anomaly_c))` for annual means.
