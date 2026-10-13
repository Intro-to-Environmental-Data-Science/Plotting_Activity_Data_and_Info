# Glacier mass balance, "reference" glaciers worldwide

**File:** `data/glacier_mass_balance.csv` · **Rows:** 68 (annual) · **Coverage:** 1956–2023

**Source:** US EPA climate indicator using data from the World Glacier Monitoring Service (WGMS), via the GitHub mirror `datasets/glacier-mass-balance`.
**License / use:** WGMS data are open access for scientific and educational purposes with correct citation; EPA data assumed public domain by the mirror.
**Cite as:** WGMS (2015). Fluctuations of Glaciers Database. World Glacier Monitoring Service, Zurich. doi:10.5904/wgms-fog-2015-11; US EPA, Climate Change Indicators: Glaciers.

## Variables

| Column | Description | Units |
|---|---|---|
| `year` | Year | |
| `cumulative_mass_balance_m_we` | Average cumulative change in glacier thickness across the reference glaciers; negative = net loss of ice | metres of water equivalent |
| `n_observations` | Count column labeled "Number of observations" in the source (presumably glaciers reporting that year) | count |

## Watch out for
- The baseline in this file is 1956 (value 0.000). The source README says 1945; ignore that.
- `n_observations` is `NA` for 1956. The README only describes data through 2014; later years are in the file but I could not trace their origin.
- Only two data columns (plus `year`), so this is the easiest dataset to plot. Going beyond a single line plot takes some creativity.

## Changes from source
Columns renamed; no values changed.

## Ideas to try
- `geom_line()` or `geom_point()` of mass balance over `year`.
- Plot `n_observations` over time: has the sample size changed?
- `mutate()` a new column converting to cm, or the year-to-year change.
