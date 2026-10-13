# Black cherry tree dimensions

**File:** `data/black_cherry_trees.csv` · **Rows:** 31 felled trees · **Coverage:** one measurement per tree (location not specified in source)

**Source:** The `trees` dataset distributed with R.
**License / use:** Distributed with R; no separate data license stated. Fine for classroom use.
**Cite as:** Meyer, H.A. (1953). *Forest Mensuration*. Penns Valley Publishers; Ryan, T.A., Joiner, B.L. & Ryan, B.F. (1976). *The Minitab Student Handbook*. Duxbury Press.

## Variables

| Column | Description | Units |
|---|---|---|
| `diameter_in` | Trunk diameter at 4 ft 6 in above ground (labeled `Girth` in R, but R's documentation says it is really diameter) | inches |
| `height_ft` | Tree height | feet |
| `volume_ft3` | Volume of timber | cubic feet |

## Watch out for
- Small dataset (31 points) with no categories, so grouping/faceting isn't an option. It's best for scatterplots and trend lines.
- Volume rises faster than linearly with diameter; `stat_smooth(method = "lm")` will show some curvature in the residuals.

## Changes from source
Dropped the row-number column; renamed `Girth`→`diameter_in`, `Height`→`height_ft`, `Volume`→`volume_ft3`.

## Ideas to try
- `geom_point()` of `volume_ft3` vs `diameter_in`, sized by `height_ft`, with `stat_smooth(method = "lm")`.
- `mutate()` a diameter in centimetres (`diameter_in * 2.54`) and plot that instead.
