# TreePlantr
# 🌳 To Tree or Not To Tree: GIS Planting Tool (v1.0 Beta)

This is a Python-based tool to help estimate where trees can realistically be planted in a city — taking into account not just land cover, but also legal/code restrictions and cultural considerations (like sports fields or sidewalks).

This version is **in beta** — it's fully scripted, functional, and outputs clean shapefiles and a Leaflet map, but still being tested for edge cases and real-world quirks.

---

## 🔍 What it Does

- Reclassifies land cover raster into 4 categories:  
  `Plantable`, `Not Plantable`, `Water`, and `Tree Canopy`
- Accepts user-defined **code-based** and **cultural** restriction layers with buffer distances
- Buffers restriction areas and subtracts them from plantable zones
- Flags “special case” locations (like golf courses or cemeteries)
- Optionally intersects plantable areas with **ownership** layers:
  - Right-of-way
  - Public parcels
  - Private parcels
- Saves all outputs to `_exports/` folder
- Creates a simple **interactive Leaflet map** (`planting_map.html`)
- Writes a readable text summary of stats — no fancy charts

---

## 🛠 Requirements

- Python 3.9+
- Libraries:  
  `geopandas`, `rasterio`, `folium`, `shapely`, `numpy`, `pandas`

Install with:
```bash
pip install geopandas rasterio folium shapely numpy pandas
