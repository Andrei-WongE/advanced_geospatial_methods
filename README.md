# Advanced Geospatial Methods

A repository containing an introduction to advanced geospatial methods, covering spatial analysis techniques, remote sensing, and geospatial data processing workflows.

---

## Table of Contents

- [Overview](#overview)
- [Topics Covered](#topics-covered)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This repository serves as a learning resource for advanced geospatial analysis methods. It provides code examples, notebooks, and datasets to help practitioners and students explore modern geospatial techniques, including spatial statistics, machine learning for geospatial data, remote sensing analysis, and more.

---

## Topics Covered

- **Spatial Data Handling** – Reading, writing, and manipulating vector and raster data (GeoJSON, Shapefile, GeoTIFF)
- **Coordinate Reference Systems (CRS)** – Projections, transformations, and reprojection workflows
- **Spatial Statistics** – Spatial autocorrelation (Moran's I), kriging, variograms, and interpolation methods
- **Remote Sensing Analysis** – Image classification, spectral indices (NDVI, NDWI), and change detection
- **Geospatial Machine Learning** – Spatial cross-validation, feature engineering from geographic data
- **Network Analysis** – Routing, shortest paths, and accessibility analysis
- **Web Mapping** – Creating interactive maps with Folium, Leaflet, and similar tools
- **Big Geospatial Data** – Processing large datasets with cloud-optimised formats (COG, Zarr) and distributed computing

---

## Prerequisites

The following tools and libraries are recommended:

- **Python 3.9+**
- [GeoPandas](https://geopandas.org/) – Spatial data manipulation
- [Rasterio](https://rasterio.readthedocs.io/) – Raster data I/O
- [Shapely](https://shapely.readthedocs.io/) – Geometric operations
- [PyProj](https://pyproj4.github.io/pyproj/) – Coordinate reference system handling
- [Scikit-learn](https://scikit-learn.org/) – Machine learning
- [Matplotlib](https://matplotlib.org/) / [Folium](https://python-visualization.github.io/folium/) – Visualisation
- [Jupyter](https://jupyter.org/) – Interactive notebooks

Install all dependencies with:

```bash
pip install geopandas rasterio shapely pyproj scikit-learn matplotlib folium jupyter
```

---

## Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/Andrei-WongE/advanced_geospatial_methods.git
   cd advanced_geospatial_methods
   ```

2. **Set up a virtual environment** (recommended)

   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**

   ```bash
   jupyter notebook
   ```

5. Open any notebook from the relevant topic folder and follow the instructions inside.

---

## Repository Structure

```
advanced_geospatial_methods/
├── data/               # Sample and reference datasets
├── notebooks/          # Jupyter notebooks organised by topic
│   ├── spatial_stats/
│   ├── remote_sensing/
│   ├── machine_learning/
│   └── network_analysis/
├── scripts/            # Reusable Python scripts and utility functions
├── requirements.txt    # Python dependency list
├── LICENSE
└── README.md
```

---

## Contributing

Contributions are welcome! To contribute:

1. Fork this repository.
2. Create a feature branch: `git checkout -b feature/your-topic`
3. Commit your changes: `git commit -m "Add: description of your change"`
4. Push to your fork: `git push origin feature/your-topic`
5. Open a Pull Request and describe your changes.

Please ensure any new notebooks or scripts include clear comments and follow the existing code style.

---

## License

This project is licensed under the [MIT License](LICENSE).

