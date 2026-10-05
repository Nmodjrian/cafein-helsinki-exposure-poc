# v2 CAFEIN comparison notebooks

These notebooks leave the original v1 notebooks untouched and write all new outputs under `../outputs/v2/`.

## Files
- `01_residential_pm25_exposure_v2.ipynb` — CAFEIN-style raster loading/mapping + clearly labelled residential point-exposure extension.
- `02_mobility_weighted_destination_exposure_v2.ipynb` — same destination-weighted metric, standardized around the CAFEIN PM2.5 source. This is not a native route-exposure operation.
- `03_candidate_walking_route_pm25_exposure_v2.ipynb` — replaces OSMnx/custom raster route sampling with `StreetNetwork` + `Exposure` + `DetailedItineraries`.
- `04_cycling_exposure_to_otaniemi_v2.ipynb` — CAFEIN-native bicycle exposure plus fastest vs PM2.5-weighted route comparison.

## Before running Stage 03–04
1. Use the same Python environment in CSC.
2. Install the current CAFEIN package and sample data if needed.
3. Build or place `helsinki-region-streets.cafein` in the notebook working directory, as assumed by the CAFEIN environmental-exposure documentation.
4. Run v1 and v2 separately; do not overwrite v1 outputs.

## Interpretation
Stage 03–04 are the clean methodological comparison. Stage 01–02 are not directly defined by the supplied CAFEIN route-exposure API, so they remain extensions around the CAFEIN data rather than exact native equivalents.
