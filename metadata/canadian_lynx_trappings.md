# Canadian lynx trappings, 1821–1934

**File:** `data/canadian_lynx_trappings.csv` · **Rows:** 114 (annual) · **Coverage:** 1821–1934, Canada

**Source:** The `lynx` dataset distributed with R, taken from Brockwell & Davis (1991); appears to be the series analyzed by Campbell & Walker (1977).
**License / use:** Distributed with R; no separate data license stated. Fine for classroom use.
**Cite as:** Brockwell, P.J. & Davis, R.A. (1991). *Time Series and Forecasting Methods*, 2nd ed. Springer; Campbell, M.J. & Walker, A.M. (1977). *J. Royal Statistical Society A* 140:411–431.

## Variables

| Column | Description | Units |
|---|---|---|
| `year` | Year | |
| `lynx_trapped` | Number of lynx trapped that year | count |

## Watch out for
- Trapping counts reflect both lynx abundance and trapping effort, so treat them as an imperfect proxy for population size.
- Two columns only: the interest is in the shape over time.

## Changes from source
Dropped the row-number column; renamed `time`→`year`, `value`→`lynx_trapped`.

## Ideas to try
- `geom_line()` with `geom_point()` added on the same plot.
- How regular are the peaks? Roughly how many years apart are they?
- `filter()` to one century and compare the amplitude of the cycles.
