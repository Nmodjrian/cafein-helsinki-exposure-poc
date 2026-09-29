# CAFEIN Helsinki environmental-exposure proof of concept

This repository reorganizes the Helsinki PM₂.₅ proof-of-concept workflow into three reproducible Jupyter notebooks. CAFEIN supplies the Helsinki sample datasets; the exposure calculations are analytical steps built on top of those data.

## Notebooks

1. **`01_residential_pm25_exposure.ipynb`**  
   FMI-ENFUSER PM₂.₅ + CAFEIN population grid → PM₂.₅ sampled at populated 250 m grid-cell centroids.

2. **`02_mobility_weighted_destination_exposure.ipynb`**  
   CAFEIN weekday OD flows + neighbourhood PM₂.₅ → trip-weighted destination PM₂.₅, environmental coverage, and origin-versus-destination exposure change.

3. **`03_candidate_walking_route_pm25_exposure.ipynb`**  
   Route-ready OD pairs + OSMnx walking network → candidate shortest walking routes, PM₂.₅ sampled every 20 m, estimated walking time, and ambient PM₂.₅ concentration–time burden.

## Conceptual progression

```text
Residential / populated-location exposure
                  ↓
Mobility-weighted destination exposure
                  ↓
Candidate route concentration–time exposure
```

The repository is a **methodological proof of concept**. The CAFEIN weekday OD flows are mobility-flow proxies; they do not identify walking mode or observed route trajectories. The FMI sample raster used in the route notebook represents a single model hour, so the route analysis is spatial rather than a time-varying event analysis.

## Next extension

A date-specific historical mobile-phone OD or presence dataset can add a fourth analytical layer: behavioural adaptation during high PM₂.₅ or heat. Useful outcomes include changes in trip volume, home-area presence, trip timing, travel distance, destination choice, and movement toward cleaner/cooler areas.

## Installation

A minimal environment is listed in `requirements.txt`. Notebook 03 downloads an OpenStreetMap walking network with OSMnx, so its first routing run requires internet access.

## Data provenance

The notebooks access sample paths exposed by `cafein.sampledata.helsinki`, including the FMI-ENFUSER air-quality raster, population grid, weekday OD/presence tables, and neighbourhood polygons.
