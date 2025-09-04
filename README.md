# Smart Monitoring using IoT–GIS Integration: Case Studies from IIT Kanpur

This repository showcases **IoT–GIS integration for smart monitoring** at IIT Kanpur, combining **low-cost IoT sensing** with **geospatial analysis** to build actionable, interactive maps. Workflows span from **data collection** to **decision support**, using Python, Jupyter, and web mapping (Leaflet/Folium).

---

## ✨ Highlights

- **IoT → GIS pipeline**: Convert sensor streams (temperature, humidity, gas, noise) into spatially referenced datasets.  
- **Actionable outputs**: Heatmaps, hotspot detection, and **fire-escape route simulations** for emergency planning.  
- **Reproducible workflows**: Well-commented Jupyter notebooks, easy to extend for new campuses or cities.  

---

## 📁 Repository Structure

smart-monitoring-iot-gis/
├── notebooks/
│ └── Fire_Escape.ipynb # Evacuation simulation (rename from Fie Esape.ipynb)
├── data/
│ ├── sensors/ # Raw IoT CSV/JSON logs
│ └── basemaps/ # Optional geojson/shapefiles
├── maps/
│ └── exports/ # Generated interactive maps (HTML)
├── src/
│ ├── io/ # Data loaders/savers
│ ├── processing/ # Cleaning, QC, filters, ENL/MSE, etc.
│ └── viz/ # Plotting & web map utilities
├── requirements.txt
└── README.md

yaml
Copy code

---

## 🧪 Case Studies

### 1) Campus Environmental Heatmaps (Temp–Humidity–Gas)
- **Goal**: Visualize temperature, humidity, and gas data as spatial heatmaps.  
- **Benefit**: Identify hotspots, ventilation issues, and intervention areas.  
- **Output**: `maps/exports/iitk_env_heatmap.html` (interactive).  

### 2) Noise Pollution Mapping
- **Goal**: Interpolate decibel values from IoT/mobile nodes into continuous surfaces.  
- **Benefit**: Support planning of quiet zones around hostels and libraries.  
- **Output**: `maps/exports/iitk_noise_map.html` (interactive).  

### 3) Fire-Escape Route Simulation (Dual-Criteria)
- **Goal**: Compute evacuation routes balancing **gas concentration** and **distance**.  
- **Benefit**: Provide rapid situational awareness and safer evacuation planning.  
- **Output**: `maps/exports/iitk_fire_escape_dual_criteria.html` (interactive).  
- **Notebook**: `notebooks/Fire_Escape.ipynb`.  

---

## 🗃️ Data Schema (Example)

| field         | type     | description                                  |
|---------------|----------|----------------------------------------------|
| timestamp     | datetime | ISO 8601 timestamp (e.g., 2025-09-04T20:10)  |
| node_id       | string   | Unique sensor/node identifier                |
| lat, lon      | float    | WGS84 coordinates                            |
| temperature_c | float    | °C                                           |
| humidity_pct  | float    | %                                            |
| gas_ppm       | float    | Gas concentration (PPM)                      |
| noise_db      | float    | A-weighted decibels                          |
| notes         | string   | Optional remarks                             |

> Store raw logs under `data/sensors/` and use `src/processing/` scripts to prepare cleaned datasets.

---

## ⚙️ Requirements

Minimal dependencies (extend as needed):
```txt
jupyter
numpy
pandas
geopandas
shapely
folium
branca
matplotlib
networkx
scikit-learn
For dashboards:

nginx
Copy code
streamlit
plotly
▶️ Quickstart
Clone the repo and open a terminal in the root folder.

(Optional) Create a virtual environment:

bash
Copy code
python -m venv .venv
# Windows
.venv\Scripts\activate
# Linux/Mac
source .venv/bin/activate
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Run notebooks:

bash
Copy code
jupyter notebook
# open notebooks/Fire_Escape.ipynb
Open generated maps under maps/exports/ in your browser.
