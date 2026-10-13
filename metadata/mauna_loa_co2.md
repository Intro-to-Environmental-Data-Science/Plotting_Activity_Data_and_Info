# Atmospheric CO2 at Mauna Loa, Hawaii (monthly)

**File:** `data/mauna_loa_co2.csv` · **Rows:** 822 · **Coverage:** March 1958 – August 2026, every month present

**Source:** NOAA Global Monitoring Laboratory and Scripps Institution of Oceanography, via the GitHub mirror `datasets/co2-ppm`.
**License / use:** NOAA data are public domain, but NOAA asks that you not claim them as your own, not imply NOAA endorsement, and not present modified data as official NOAA data. The mirror's packaging is ODC-PDDL.
**Cite as:** Tans, P. (NOAA/GML) and Keeling, R. (Scripps). Trends in Atmospheric Carbon Dioxide, Mauna Loa. gml.noaa.gov/ccgg/trends/

## Variables

| Column | Description | Units |
|---|---|---|
| `date` | First day of the month (a real date) | |
| `year`, `month` | Pulled out of `date` for convenience | |
| `decimal_date` | Year as a decimal, e.g. 1958.2027 | years |
| `co2_ppm` | Monthly mean CO2 (dry-air mole fraction) | ppm |
| `co2_ppm_deseasonalized` | Same, with the seasonal cycle removed | ppm |
| `n_days` | Days of measurements used that month | days |

## Watch out for
- Strong yearly sawtooth: CO2 peaks around May and bottoms out around September/October. Plotting one year, one decade, and the full record tells different stories.
- `n_days` is `NA` before 1976 (not reported).

## Changes from source
- The source file has a 6-name header over 7-field rows, so its labels were shifted. I assigned names in what appears to be the order of NOAA's current monthly file. The seasonal pattern of `co2_ppm - co2_ppm_deseasonalized` (about +3 ppm in May, about -3 ppm in Sep/Oct) matches the known Mauna Loa cycle, **but I could not cross-check against NOAA's own file** (automated access is blocked). Spot-check a few values at gml.noaa.gov/ccgg/trends/data.html before relying on it.
- Dropped the standard-deviation and uncertainty columns; `-1` placeholders in `n_days` set to `NA`; `date` converted to YYYY-MM-DD; `year` and `month` added.

## Ideas to try
- `geom_line()` of `co2_ppm` over `date`, then compare with `co2_ppm_deseasonalized`.
- `filter()` to a single decade and see the seasonal cycle.
- `group_by(year)` + `summarize(mean(co2_ppm))` for annual means.
