# Global average sea level change since 1880

**File:** `data/sea_level.csv` · **Rows:** 144 (annual) · **Coverage:** 1880–2023

**Source:** US EPA climate indicator compiling CSIRO (tide gauges) and NOAA (satellite altimetry), via the GitHub mirror `datasets/sea-level-rise`.
**License / use:** EPA data are US Government (assumed public domain by the mirror). CSIRO asks that its figures be acknowledged and not altered.
**Cite as:** Church, J.A. & White, N.J. (2011). Sea-level rise from the late 19th to the early 21st century. *Surveys in Geophysics*, doi:10.1007/s10712-011-9119-1; US EPA, Climate Change Indicators: Sea Level.

## Variables

| Column | Description | Units |
|---|---|---|
| `year` | Year | |
| `csiro_sea_level_inches` | Cumulative change in global average sea level (CSIRO reconstruction), 0 at 1880 | inches |
| `csiro_lower_bound_inches`, `csiro_upper_bound_inches` | Error bounds around the CSIRO value | inches |
| `noaa_sea_level_inches` | Cumulative change from satellite measurements | inches |

## Watch out for
- Two series with different coverage: CSIRO is `NA` for 2014–2023; NOAA is `NA` before 1993. Overlap is 1993–2013.
- Units are **inferred**: the file and README don't state them, but the CSIRO value for 2009 is 8.5 in (about 217 mm), consistent with the roughly 210 mm rise the source reports for 1880–2009.
- The source README describes data through 2014; later years are in the file but I could not trace where they came from.

## Changes from source
Columns renamed to include units; no values changed.

## Ideas to try
- `geom_line()` of one series, then add a second `geom_line()` for the other (multiple geoms).
- `filter(year >= 1993)` to compare the two methods where they overlap.
