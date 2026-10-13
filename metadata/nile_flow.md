# Annual flow of the River Nile at Aswan, 1871–1970

**File:** `data/nile_flow.csv` · **Rows:** 100 (annual) · **Coverage:** 1871–1970

**Source:** The `Nile` dataset distributed with R, from Durbin & Koopman (2001).
**License / use:** Distributed with R; no separate data license stated. Fine for classroom use.
**Cite as:** Durbin, J. & Koopman, S.J. (2001). *Time Series Analysis by State Space Methods*. Oxford University Press; Cobb, G.W. (1978). The problem of the Nile. *Biometrika* 65:243–251.

## Variables

| Column | Description | Units |
|---|---|---|
| `year` | Year | |
| `annual_flow_1e8_m3` | Total annual flow at Aswan | 10^8 m³ (100 million cubic metres) |

## Watch out for
- R's documentation notes an "apparent changepoint near 1898" in this series (from Cobb 1978). Can you see it by eye?
- A single short time series: the simplest hydrology option, but not much to facet or color by.

## Changes from source
Dropped the row-number column; renamed `time`→`year`, `value`→`annual_flow_1e8_m3`.

## Ideas to try
- `geom_line()` plus `geom_point()`, with `stat_smooth()` added.
- `filter(year < 1899)` vs `filter(year >= 1899)` and compare the means with `summarize()`.
- Same plot styled with different themes (`theme_classic()`, `theme_bw()`).
