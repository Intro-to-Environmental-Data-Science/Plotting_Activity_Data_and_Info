# New York City air quality and weather, summer 1973 (daily)

**File:** `data/nyc_air_quality_1973.csv` · **Rows:** 153 days · **Coverage:** 1 May – 30 September 1973

**Source:** The `airquality` dataset distributed with R. Ozone from the New York State Department of Conservation; meteorological data from the National Weather Service.
**License / use:** Distributed with R; the documentation states no separate data license. Fine for classroom use.
**Cite as:** New York State Department of Conservation and National Weather Service, via R `datasets::airquality`.

## Variables

| Column | Description | Units |
|---|---|---|
| `date` | Calendar date (a real date) | |
| `ozone_ppb` | Mean ozone, 1300–1500 h, Roosevelt Island | parts per billion |
| `solar_radiation_lang` | Solar radiation, 0800–1200 h, Central Park (4000–7700 Å band) | langleys |
| `wind_mph` | Average wind speed, 0700 and 1000 h, LaGuardia Airport | mph |
| `temp_max_f` | **Maximum** daily temperature, LaGuardia Airport | °F |
| `month`, `day` | Month (5–9) and day of month | |

## Watch out for
- Missing values: `ozone_ppb` has 37 `NA`s and `solar_radiation_lang` has 7. Lines will have gaps; `mean(ozone_ppb, na.rm = TRUE)` is needed for summaries.
- `month` is a number, so ggplot treats it as continuous. For a boxplot by month you need `as.factor(month)` (a stretch goal, not something we have covered).

## Changes from source
Dropped the row-number column; renamed columns to lowercase with units (`Ozone`→`ozone_ppb`, `Solar.R`→`solar_radiation_lang`, `Wind`→`wind_mph`, `Temp`→`temp_max_f`, `Month`→`month`, `Day`→`day`); added `date`.

## Ideas to try
- Scatterplot of `temp_max_f` vs `ozone_ppb`, sized or colored by `wind_mph`.
- `geom_line()` of ozone over `date`.
- `filter(month == 7)` and compare with August.
