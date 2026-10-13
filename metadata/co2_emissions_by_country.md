# CO2 emissions by country, 1950–2024

**File:** `data/co2_emissions_by_country.csv` · **Rows:** 16,350 (one per country per year) · **Coverage:** 218 countries, 1950–2024

**Source:** Our World in Data CO2 and Greenhouse Gas Emissions dataset (`owid/co2-data`), built mainly on the Global Carbon Budget (2025), with population and GDP (Maddison Project Database 2023) added.
**License / use:** CC BY 4.0 — credit Our World in Data and the original sources. Some third-party components carry their own terms (see the OWID README).
**Cite as:** Our World in Data, CO2 and Greenhouse Gas Emissions. github.com/owid/co2-data. Underlying data: Global Carbon Project, Global Carbon Budget 2025.

## Variables

| Column | Description | Units |
|---|---|---|
| `country`, `iso_code` | Country name and 3-letter ISO code | |
| `year` | Year | |
| `population` | Population | people |
| `gdp` | Total economic output, adjusted for inflation and cost of living | international-$ (2011 prices) |
| `co2` | Annual CO2 emissions, excluding land-use change | million tonnes |
| `co2_per_capita` | CO2 emissions per person | tonnes per person |
| `coal_co2`, `oil_co2`, `gas_co2`, `cement_co2` | CO2 emissions by source | million tonnes |

## Watch out for
- 218 countries is far too many lines for one plot. Use `filter(country %in% c("United States", "China", ...))`.
- Missing values are common: `gdp` (4,893 NA), `gas_co2` (8,343 NA), `co2` (1,080 NA). Some countries only appear partway through the record.
- Total emissions and per-person emissions tell very different stories. Try both.

## Changes from source
Kept only rows for countries (dropped regional/income-group aggregates and "World"), only 1950 onward, and 11 of the original 79 columns.

## Ideas to try
- `geom_line()` of `co2_per_capita` for 4–6 countries, `color = country`.
- `filter(year == 2023)` and plot `gdp` vs `co2_per_capita`, with `scale_x_log10()`.
- `group_by(country)` + `summarize(max(co2))` to find the largest emitters.
