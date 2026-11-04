# Data sources

All files in this folder are original downloads and are never edited.

**Access date for all files:** 03-Nov-2026

| File | Publisher | Where to download | Licence | Size |
|---|---|---|---|---|
| `SAPS_2022_Small_Area_UR_171024.csv` | Central Statistics Office (CSO) | https://www.cso.ie/en/census/census2022/census2022smallareapopulationstatistics/ → "CSO Small Areas 2022" CSV | CC BY 4.0 | 18,920 rows x 795 columns |
| `Small_Area_National_Statistical_Boundaries_2022_Ungeneralised_view_-4936014253783534521.csv` | Tailte Éireann (formerly Ordnance Survey Ireland) | https://data-osi.opendata.arcgis.com/datasets/osi::cso-small-areas-national-statistical-boundaries-2022-ungeneralised -> "Download" -> "CSV"|
| `Glossary_Saps_2022_REVISED_21102024.xlsx` | CSO | https://www.cso.ie/en/census/census2022/census2022smallareapopulationstatistics/ → "SAPS 2022 Glossary (XLS 34KB)" CSV | CC BY 4.0 | 790 column descriptions |

## How the files relate

- **One row = one CSO Small Area** (an area of usually 80–120 dwellings). There are 18,919 small areas.
- The SAPS file holds the census counts. The boundary file holds each area's land area (`Shape__Area`, in square metres) plus county and region names.
- **Join key:** `GUID` (SAPS) = `SA_GUID_2022` (boundaries). All 18,919 areas match one-to-one; there are no unmatched rows on either side.
- `GEOGID` is **not** used as the join key: about 2,000 SAPS codes are merged codes (e.g. `017008002/017008001`), and the boundary file's code has an `A` prefix (`A017010016`).
- The glossary decodes the SAPS column codes (e.g. `T6_8_OVD` = "Other vacant dwellings").
