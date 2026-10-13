# Palmer Archipelago penguins

**File:** `data/penguins.csv` · **Rows:** 344 penguins · **Coverage:** 3 species on 3 islands near Palmer Station, Antarctica; 2007–2009

**Source:** Palmer Station Antarctica LTER (Dr. Kristen Gorman), packaged by the `palmerpenguins` R package.
**License / use:** CC0 (public domain dedication).
**Cite as:** Gorman, K.B., Williams, T.D. & Fraser, W.R. (2014). Ecological sexual dimorphism and environmental variability within a community of Antarctic penguins (genus *Pygoscelis*). *PLoS ONE* 9(3): e90081. Package: allisonhorst.github.io/palmerpenguins

## Variables

| Column | Description | Units |
|---|---|---|
| `species` | Adelie (152), Gentoo (124), Chinstrap (68) | |
| `island` | Biscoe (168), Dream (124), Torgersen (52) | |
| `bill_length_mm`, `bill_depth_mm` | Bill dimensions | mm |
| `flipper_length_mm` | Flipper length | mm |
| `body_mass_g` | Body mass | g |
| `sex` | `male` / `female` | |
| `year` | Study year (2007, 2008, 2009) | |

## Watch out for
- Missing values: 2 penguins have no measurements at all, and `sex` is `NA` for 11. ggplot will warn "Removed 2 rows containing missing values", which is a good moment to discuss `NA`s.
- Species overlap in some measurements but separate cleanly in others. Which pair of variables separates them best?

## Changes from source
None (the file is the package's raw CSV).

## Ideas to try
- `geom_point()` of flipper length vs body mass, `color = species`.
- Boxplot of `body_mass_g` by `species`, then `facet_wrap()` by `island`.
- Add `stat_smooth(method = "lm")` to see the relationship within each species.
