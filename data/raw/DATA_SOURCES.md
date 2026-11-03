# Data sources

All files in this folder are original downloads and are never edited. Cleaning happens in the notebook, and outputs go to `data/processed/`.

**Access date for all files:** 03-Nov-2026

| File | Publisher | Where to download | Licence | Size |
|---|---|---|---|---|
| `SAPS_2022_Small_Area_UR_171024.csv` | Central Statistics Office (CSO) | https://www.cso.ie/en/census/census2022/census2022smallareapopulationstatistics/ → "CSO Small Areas 2022" CSV (version that includes the urban/rural category) | CC BY 4.0 | 18,920 rows x 795 columns |
| `Small_Area_National_Statistical_Boundaries_2022_Ungeneralised_view_-4936014253783534521.csv` | Tailte Éireann (formerly Ordnance Survey Ireland), via data.gov.ie | https://data.gov.ie/dataset/cso-small-areas-national-statistical-boundaries-2022-ungeneralised1 → CSV | CC BY 4.0 | 18,919 rows x 28 columns |
| `Glossary_Saps_2022_REVISED_21102024.xlsx` | CSO | Same CSO page as the SAPS file → "SAPS 2022 Glossary" | CC BY 4.0 | 790 column descriptions |

## How the files relate

- **One row = one CSO Small Area** (an area of usually 80–120 dwellings). There are 18,919 small areas.
- The SAPS file holds the census counts. The boundary file holds each area's land area (`Shape__Area`, in square metres) plus county and region names.
- **Join key:** `GUID` (SAPS) = `SA_GUID_2022` (boundaries). All 18,919 areas match one-to-one; there are no unmatched rows on either side.
- `GEOGID` is **not** used as the join key: about 2,000 SAPS codes are merged codes (e.g. `017008002/017008001`), and the boundary file's code has an `A` prefix (`A017010016`).
- The glossary decodes the SAPS column codes (e.g. `T6_8_OVD` = "Other vacant dwellings").

## Notes found during checking

- The SAPS file's last row is the **national total** (`GEOGID = "Ireland"`). It is not a small area and is removed in Phase 3.
- `Shape__Area` adds up to 70,265 km², which matches the area of the State, so it is true area in square metres.
- **Considered but not used:** `SAPS_2022_BUA_270923.csv` (the same census tables summed for 867 towns / Built-Up Areas). It has no key linking small areas to towns, so it cannot be joined. It is not included in the repository.
