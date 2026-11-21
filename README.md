# EDS220 HW4: Visualizing the Eaton Fire and Palisades Fire through False Color Images

<img width="1600" height="1067" alt="Palisades_Fire_(54254895365)" src="https://github.com/user-attachments/assets/564d526a-f72d-4a6e-9dfe-6c4170f636b3" />


## Purpose
This repository analyzes the scale and false color imagery of the Eaton Fire and Palisades Fire. In early January 2025, the Eaton and Palisades Fires ignited almost at the same time in Los Angeles County. The fires are visualized in this notebook through false-color satellite imagery which helps visualize the vegetation health, burn severity, and fire extent by displaying infrared wavelengths as visible colors. The fire perimeters combined with the Landsat8 image show the burn scars of the two fires. The final map is produced as a false-color image map to better highlight the burn scars compared to the surrounding vegetation.

## Overview
Highlights:
- hwk4-task2-false-color-BERRY.ipynb file: True color and false color analysis of Eaton and Palisades fires. 
- Data folder: houses the Eaton Perimeter Data, Palisades Perimeter Data, and Landsat-8 dataset (collected in 2/23/2025).

```{r}
eds220-hwk4
│--  README.md
│--  hwk4-task2-false-color-BERRY.ipynb
│--  .gitignore
```
## Highlights of Analysis
- Restore and match the different CRSs of different datasets.
      - landsat.rio.write_crs("EPSG:32611", inplace=True)
      - palisades = palisades.to_crs(landsat.rio.crs)
- Plot of true-color imagery (red, green, and blue bands) which shows what the human eye can see.
- Plot of false-color imagery (swir22, nir08, and red bands) to show a greater visual contrast between different types of landscapes, especially highlighting the burned areas.

## Data Access and Summary
*First dataset*: Landsat Collection 2 Level-2 atmospherically:

- _landsat8-2025-02-23-palisades-eaton.nc_: collection of bands (red, green, blue, near-infrared and shortwave infared)

*Summary*: This data comes from the Microsoft Planetary Computer. This is a landsat Collection 2 Level-2 Science Products, consisting of atmospherically corrected surface reflectance and surface temperature image data from 1982 to present day. This dataset is specifically from February 23, 2025.

*Second dataset*: Fire perimeters for the Eaton and Palisades fires:

- _Eaton_Perimeter_20250121_
- _Palisades_Perimieter_20250121_

*Summary*: These datasets were derived from CAL FIRE’s Historical Fire Perimeter Dataset, which provides daily snapshots of wildfire perimeters. Individual daily boundary polygons were combined for each fire to create a single burn perimeter representing the full extent of the fire. 

## Author
Nina Berry: https://github.com/nberry18 

## References

County of Los Angeles. (2025). Palisades and Eaton Dissolved Fire Perimeters (2025)[Dataset]. County of Los Angeles. https://data.lacounty.gov/maps/ad51845ea5fb4eb483bc2a7c38b2370c/about

Landsat Collection 2 Level-2. Landsat 8[Dataset]. Microsoft Planetary Computer. https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2
