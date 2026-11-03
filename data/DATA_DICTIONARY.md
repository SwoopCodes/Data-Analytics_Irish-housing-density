# Data dictionary

The full list of 790 census columns and their meanings is in `data/raw/Glossary_Saps_2022_REVISED_21102024.xlsx`. This file lists only the columns this project uses.

## Identifier and context columns

| Column | File | Meaning |
|---|---|---|
| `GUID` | SAPS | Unique ID of the small area (join key) |
| `GEOGID` | SAPS | CSO small area code (read as text; some are merged codes) |
| `UR_Category_Desc` | SAPS | CSO six-way urban/rural classification (Cities → Highly rural/remote) |
| `SA_GUID_2022` | Boundaries | Unique ID of the small area (join key) |
| `Shape__Area` | Boundaries | Land area of the small area in square metres |
| `COUNTY_ENGLISH` | Boundaries | County name |
| `SA_NUTS3_NAME` | Boundaries | NUTS3 region name |

## Clustering features (8)

Codes were checked against the CSO glossary. `H` = households.

| Feature | Formula | Glossary meaning of source columns |
|---|---|---|
| `log_dwellings_per_km2` | log of `T6_8_T` ÷ (`Shape__Area` ÷ 1,000,000) | T6_8_T = total permanent dwellings (Table 6.8, occupancy status) |
| `pct_flats` | `T6_1_FA_H` ÷ `T6_1_TH` | Flat/Apartment households ÷ total private households |
| `pct_built_2011_on` | (`T6_2_11_15H` + `T6_2_16LH`) ÷ `T6_2_TH` | Households in homes built 2011–2015 + 2016 or later ÷ total permanent private households |
| `vacancy_rate` | `T6_8_OVD` ÷ `T6_8_T` | Other vacant dwellings ÷ total permanent dwellings |
| `holiday_home_rate` | `T6_8_UHH` ÷ `T6_8_T` | Unoccupied holiday homes ÷ total permanent dwellings |
| `persons_per_household` | `T6_1_TP` ÷ `T6_1_TH` | Persons in private households ÷ private households |
| `pct_renting` | (`T6_3_RPLH` + `T6_3_RLAH` + `T6_3_RVCHBH`) ÷ `T6_3_TH` | Rented from private landlord + local authority + voluntary/co-op housing body ÷ total permanent private households |
| `pct_public_transport` | (`T11_1_BUW` + `T11_1_TDLW`) ÷ `T11_1_TW` | Bus, minibus or coach + Train, DART or LUAS (to work) ÷ total travelling to work |

**Removed:** `pct_car` (car driver + car passenger to work ÷ total). It was strongly negatively correlated with `pct_public_transport` (r = −0.65), so keeping both would count commuting twice in the clustering.

**Note:** Table 6.1 counts *all* private households, including temporary dwellings such as caravans. Tables 6.2 and 6.3 count *permanent* private households only. Each feature therefore uses its own table's total.
