# Data Notes

## earthquakes_2020_2025.csv

A saved snapshot of the USGS Earthquake Catalog API pull used in the proposal notebook: every earthquake of magnitude 6.0 or higher from 2020 to 2025. It has 795 rows. Source: https://earthquake.usgs.gov/fdsnws/event/1/

The file is a plain CSV. It was originally named with an .xls extension, which is why it is stored here as .csv.

| Column | Meaning |
|---|---|
| `place` | Location text from the USGS |
| `time` | Date and time of the earthquake (UTC) |
| `mag` | Magnitude |
| `depth_km` | Depth in km |
| `longitude`, `latitude` | Epicenter coordinates |
| `mmi` | Estimated strongest shaking (Modified Mercalli Intensity) |
| `felt` | Number of Did You Feel It reports |
| `sig` | USGS significance score |
| `alert` | PAGER alert color (green, yellow, orange, red) |
| `mag_type` | Method used to measure magnitude |
| `tsunami` | USGS tsunami flag (1 or 0) |

Known gaps in this file: 141 rows have no `felt` value, 1 row has no `mmi`, and 1 row has no `alert`. Some rows also have an `mmi` of 0, which means the USGS made no shaking estimate. The Phase II notebook handles all of these.

## World Bank data

Population density and GDP per capita are pulled live from the World Bank API inside the Phase II notebook, so they are not stored here. Source: https://datahelpdesk.worldbank.org/knowledgebase/topics/125589

## Note on reruns

The Phase II notebook pulls from the live API and keeps the cleaned result in memory and in a local `earthquakes_clean.csv`. The USGS revises older records, so a new pull can differ slightly from this snapshot.
