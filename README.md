# Amazon Basin Archaeological Search with Open Data & Models (Unsloth Gemma 3)

This project uses open-source vision-language models (e.g., **Gemma-3B-Vision**) to scan and analyze Sentinel-2 satellite imagery tiles for possible archaeological earthworks — such as geoglyphs, mounds, and geometric clearings.

The pipeline integrates **geospatial filtering**, **batch inference**, and **interactive mapping** tools for semi-automated archaeological prospecting.

> ⚙️ *Note: GPT-4.0, o4, and o3 were used for ideation, prototyping, and debugging.*

---

## Key Features

- Sentinel-2 False Colour Composite (NIR-Red-Green) analysis  
- NDVI prefiltering & automated tile generation (1 km² PNGs)  
- Batch inference using **Unsloth Gemma 3 Vision**  
- Interactive maps with tile previews and AI-generated descriptions  
- No credentials, no API keys — completely open-access  
- Modular, extensible notebooks for scientific use  

---

## Pipeline Overview

### 1. **Tile Generation & Filtering**
- Automatically chunks large raster into square tiles.
- Filters based on:
  - Mean NDVI (vegetation index)
  - Image brightness / coverage
  - Removal of mostly black or empty tiles
- Output: `candidates.csv` with tile paths + UTM coordinates.

### 2. **Gemma 3 Vision Inference**
- Efficient batch processing via HuggingFace Datasets.
- Natural language prompts + tile images → archaeological triage.
- Robust parsing and output handling.

### 3. **Results Merging & Mapping**
- Inference results are joined back to candidate data.
- UTM coordinates are converted to lat/lon.
- Interactive **Folium** maps generated:
  - Clickable markers
  - Popups with tile image and Gemma’s analysis

---

## 🗺Visualization Outputs

- False Colour Composite maps  
- Interactive detection maps (HTML)  
- Exportable CSVs with AI annotations  

---

## Optional Steps (Planned / In Progress)
- Tile-level statistical filtering  
- Hillshade or DEM analysis (API limitations prevented for now)  
- Fine-tuning support for archaeological use cases  

---

## Data Sources

- **Sentinel-2** imagery (via AWS Open Data Registry)  
- **Open-source models**: Gemma-3B-Vision (Unsloth weights)

---

## Requirements

- GPU recommended  
- Python 3.8+  
- `folium`, `rasterio`, `pandas`, `transformers`, `datasets`, `unsloth`, etc.

---

## Author Notes

This repository was developed iteratively through Kaggle Notebooks and linked to GitHub for sharing and further development. Work is still in progress.

