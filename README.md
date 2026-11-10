# Irish Housing Density: Clustering Census 2022 Small Areas

**Module:** Data Analytics, CA2 (CRISP-DM Analytics Project)
**Student:** Patryk Graszk, T00257714 , MTU Kerry
**Lecturer:** Andrew Shields

### Project question

Can Irish small areas be grouped into distinct housing-pattern types to help planners identify low-density areas that are well placed for additional housing, in line with the compact growth goals of the National Planning Framework?

### Data

| File | Source | Licence |
|---|---|---|
| `SAPS_2022_Small_Area_UR_171024.csv` | CSO Census 2022 Small Area Population Statistics | CSO open data (CC BY 4.0) |
| `Small_Area_National_Statistical_Boundaries_2022_Ungeneralised_view_....csv` | Tailte Éireann Open Data Portal| CC BY 4.0 |
| `Glossary_Saps_2022_REVISED_21102024.xlsx` | CSO column glossary | CSO open data (CC BY 4.0) |

Place all raw files in `data/raw/`. Raw files are never edited. Download links and file notes are in `data/raw/DATA_SOURCES.md`; the features used are defined in `data/DATA_DICTIONARY.md`.

### Method

K-means clustering of 18,919 small areas on eight features (log dwelling density, % flats, % built since 2011, vacancy rate, holiday-home rate, persons per household, % renting, % public transport commuting). Data is joined on the small area GUID and standardised before clustering.

### Repository structure

- `notebooks/` – main CRISP-DM notebook
- `data/raw/` – original downloads
- `data/processed/` – cleaned data produced by the notebook
- `figures/` – charts used in the paper
- `paper/` – research paper
- `references/` – reference list
- `AI_LOG.md` – record of AI assistance


### Project status

| Phase | Status |
|---|---|
| 1. Business Understanding | Drafted |
| 2. Data Understanding | Not started |
| 3. Data Preparation | Not started |
| 4. Modelling | Not started |
| 5. Evaluation | Not started |
| 6. Deployment & Reflection | Not started |
| Paper | Not started |
| AI Collaboration Statement | Not started |
