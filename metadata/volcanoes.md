# Volcanoes of the world

**File:** `data/volcanoes.csv` · **Rows:** 958 volcanoes in 89 countries · **Coverage:** global

**Source:** Smithsonian Institution Global Volcanism Program, via TidyTuesday (2020-05-12).
**License / use:** Redistributed by TidyTuesday for educational use. I did not find a license statement in that repo, so check the Smithsonian GVP terms (volcano.si.edu) before reusing beyond class.
**Cite as:** Global Volcanism Program, Smithsonian Institution. volcano.si.edu

## Variables

| Column | Description | Units |
|---|---|---|
| `volcano_number`, `volcano_name` | ID and name | |
| `primary_volcano_type` | Volcano type (26 values, e.g. Stratovolcano, Shield, Caldera) | |
| `last_eruption_year` | Year of last known eruption. **Negative = BCE** (e.g. -6850) | year |
| `country`, `region`, `subregion` | Location (19 regions) | |
| `latitude`, `longitude` | Location | decimal degrees |
| `elevation` | Summit elevation; negative for submarine volcanoes | metres (units not stated in source; values are consistent with metres) |
| `tectonic_settings` | Plate-tectonic setting and crust type | |
| `evidence_category` | Type of evidence for the last eruption | |
| `population_within_5_km` … `_100_km` | People living within 5, 10, 30, 100 km | people |

## Watch out for
- `last_eruption_year` is `NA` for 301 volcanoes (`"Unknown"` in the source).
- Near-duplicate categories: `Stratovolcano` (353) and `Stratovolcano(es)` (107), `Shield` and `Shield(s)`, are separate values.
- Many long text labels; boxplots by type may need `filter()` to a few types first.

## Changes from source
Dropped the 10 rock-type columns; `last_eruption_year` converted from text to a number (`"Unknown"` → `NA`).

## Ideas to try
- `longitude` (x) vs `latitude` (y) as `geom_point()`, colored by `region` or `primary_volcano_type` — it draws a rough world map along plate boundaries.
- Boxplot of `elevation` by `primary_volcano_type` after filtering to a few types.
- `filter(country == "United States")` and plot `elevation` vs `population_within_30_km` with `scale_y_log10()`.
