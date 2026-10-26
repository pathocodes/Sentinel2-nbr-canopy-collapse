# Sentinel-2 NBR Canopy Collapse Analysis (2016–2026)

## Overview

During the 2026 dry season, forest and land fires (*karhutla*) swept across key regions in Sumatra, Papua, and Kalimantan (Reuters; Teresia, 2026). This project uses satellite remote sensing to look past the immediate surface haze and evaluate long-term landscape transformation in **Central Kalimantan, Indonesia**.

Using **Sentinel-2 multispectral imagery (NIR & SWIR)** accessed via Microsoft Planetary Computer STAC API, this study tracks Normalized Burn Ratio (NBR) dynamics over a 10-year period (2016–2026). The goal is to separate seasonal drought stress from permanent ecosystem collapse across vulnerable peatlands[cite: 1, 2].

---

## Study Area Coordinates
The spatial analysis and sample imagery focus on the vulnerable peatland corridors of Central Kalimantan, Indonesia, defined by the following geographical bounding box:
* **Area Extent:** Longitude `115.18°E` to `115.28°E`, Latitude `-2.80°S` to `-2.72°S`
* **Spatial Resolution:** 10m x 10m (Sentinel-2 Native Grid)
  
---

## Key Findings

* **53.63% Forest Degradation Rate:** Out of 94,804 analyzed pixels (10m X 10m spatial resolution), 50,840 pixels exhibited severe canopy loss (dNDVI > 0.25).
* **Permanent Canopy Collapse:** Time-series trendlines confirm that forest loss in this sample area is not a temporary seasonal dip, but a permanent structural degradation[cite: 1].
* **Peatland Vulnerability:** Fire severity maps highlight clear degradation footprints aligned with human-made drainage canals, turning moisture-rich carbon sinks into fire-prone zones[cite: 1].

---

## Visualizations

### 1. 10-Year Canopy Loss (3D Surface Topography)
A 3D mesh representation of NDVI values showing the structural flattening of the forest canopy between 2016 and 2026.

| 2016 (Dense Forest) | 2026 (Deforestation) |
| :---: | :---: |
| *High NDVI peaks indicating healthy canopy* | *Flattened topography showing 53.6% canopy loss* |

<img width="1724" height="794" alt="3d landscape 2016-2026" src="https://github.com/user-attachments/assets/f57bcee5-28a1-4dc9-a438-45e0ceb620f5" />

---

### 2. USGS Burn Severity Mapping (dNBR)
Burn severity classification using standard USGS thresholds (dNBR) to isolate exact burn scars from healthy vegetation.

<img width="919" height="658" alt="USGS Standard Burn map" src="https://github.com/user-attachments/assets/ce6788d3-e742-489f-a324-44b59f1300e9" />

## Methodology & Tech Stack

* **Data Source:** Sentinel-2 L2A via Planetary Computer STAC API.
* **Indices Computed:**
  * **NDVI** (Normalized Difference Vegetation Index) for active canopy density.
  * **NBR** (Normalized Burn Ratio) & **dNBR** (dNBR) for fire severity detection.
* **Core Libraries:** `pystac_client`, `planetary_computer`, `xarray`, `rioxarray`, `matplotlib`, `numpy`.

---
## Repository Structure

```text
sentinel2-nbr-canopy-collapse/
├── data/
│   └── raw/                   
├── notebooks/
│   └── central_kalimantan_nbr_analysis.ipynb 
├── outputs/
│   ├── figures/              
│   └── tables/                
├── .gitignore
├── LICENSE
└── README.md
```

---

## Open Source & Collaboration
This project is fully open-source under the **MIT License**. 

I welcome conservationists, NGO research teams, GIS analysts, and climate advocates to utilize, adapt, or replicate this data pipeline for other forest concessions and peatland areas across Indonesia.

For feedback or collaboration, feel free to open a [GitHub Issue](https://github.com/pathocodes/Sentinel2-nbr-canopy-collapse/issues).

---

## References & Data Sources

1. **News & Context:** 
   * Teresia, A. (2026, August 11). *Indonesia races to contain fires as haze spreads across region*. Reuters.
2. **Satellite & Remote Sensing Data:**
   * European Space Agency (ESA). *Sentinel-2 MSI (MultiSpectral Instrument) Level-2A Data*. Accessed via Microsoft Planetary Computer STAC API.
3. **Burn Severity Standards:**
   * U.S. Geological Survey (USGS). *FireMon: Landscape Assessment (LA) Standard Operating Procedures*. (Normalized Burn Ratio & dNBR classification thresholds).

