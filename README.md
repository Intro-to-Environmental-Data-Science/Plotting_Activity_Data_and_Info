# Pick a dataset and plot it

Choose **one** dataset below, read it into R, and make a few plots to explore it. Each dataset has a metadata file (source, variables, units, quirks, ideas) in `metadata/`. Read it before you start.

## Loading a dataset

```r
library(tidyverse)

dat <- read_csv("data/penguins.csv")   # swap in your file name
head(dat)
```

If R can't find the file, check that you opened this repo as an RStudio project.

## The datasets

| # | Dataset | File | Rows | Good for | Watch out for |
|---|---|---|---|---|---|
| 1 | [Atmospheric CO2, Mauna Loa](metadata/mauna_loa_co2.md) | `mauna_loa_co2.csv` | 822 | time series, seasonality | strong yearly cycle |
| 2 | [Global temperature anomalies](metadata/global_temperature_anomaly.md) | `global_temperature_anomaly.csv` | 3,871 | color/facet by source, time series | two different baselines |
| 3 | [Palmer penguins](metadata/penguins.md) | `penguins.csv` | 344 | scatter, boxplots, facets | a few `NA`s |
| 4 | [NYC air quality, summer 1973](metadata/nyc_air_quality_1973.md) | `nyc_air_quality_1973.csv` | 153 | scatter, relationships between variables | many `NA`s |
| 5 | [Volcanoes of the world](metadata/volcanoes.md) | `volcanoes.csv` | 958 | maps from lat/long, boxplots, `filter()` | near-duplicate category names |
| 6 | [CO2 emissions by country](metadata/co2_emissions_by_country.md) | `co2_emissions_by_country.csv` | 16,350 | `filter()` to countries, lines by group | 218 countries; lots of `NA`s |
| 7 | [Global sea level since 1880](metadata/sea_level.md) | `sea_level.csv` | 144 | multiple geoms, comparing two series | series cover different years |
| 8 | [Glacier mass balance](metadata/glacier_mass_balance.md) | `glacier_mass_balance.csv` | 68 | simple line/point | only two data columns |
| 9 | [Black cherry trees](metadata/black_cherry_trees.md) | `black_cherry_trees.csv` | 31 | scatter + trend line | tiny; no categories |
| 10 | [Canadian lynx trappings](metadata/canadian_lynx_trappings.md) | `canadian_lynx_trappings.csv` | 114 | time series, cycles | two columns only |
| 11 | [Nile River flow](metadata/nile_flow.md) | `nile_flow.csv` | 100 | hydrology time series | two columns only |

## About these files

Data come from public sources (NOAA, NASA, EPA, Smithsonian, Our World in Data, and others, mostly via GitHub mirrors). Where I changed anything (renamed columns, converted dates, dropped columns), it is listed under "Changes from source" in each metadata file. `prep/make_datasets.py` rebuilds every file from its source.
