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
