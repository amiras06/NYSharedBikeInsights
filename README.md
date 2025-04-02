# NYSharedBikeInsights

This repository contains a project analyzing the historical dataset of New York City shared bikes (Citibikes). The analysis covers data from 2014 to 2023 and leverages Big Data tools (Spark or Dask) to perform data acquisition, cleaning, transformation, exploratory analysis, and spatial visualizations.

## Project Overview

The project tasks include:
- **Data Acquisition:**  
  Programmatically download CSV files for each year (2014 to 2023) using Python's `requests` module. The downloaded files are stored in a dedicated `data/` directory.
  
- **Data Transformation:**  
  Convert the CSV files into a more efficient format (Parquet or ORC) suitable for Big Data processing. This involves:
  - Renaming columns to ensure consistency.
  - Standardizing timestamp formats.
  - Handling schema evolution and dealing with variations in station identifiers.

- **Data Modeling:**  
  Organize the transformed data into a star schema with:
  - A dimension table for station information (name, id(s), latitude, longitude, etc.).
  - An event table for trips, linking to the station dimension.

- **Exploratory Analysis & Visualization:**  
  - Analyze trip distance distributions, trip counts by pickup/dropoff pairs, and seasonal trends.
  - Generate time series plots (e.g., number of pickups/docks, average trip duration).
  - Perform spatial analysis with heatmaps and interactive choropleth maps using GPS coordinates.
  
- **Performance Monitoring:**  
  Investigate Spark/Dask job execution by examining logical and physical plans, partitioning strategies, and shuffle operations.

## Requirements

- **Python 3.x**
- **Big Data Tools:** Spark (version ≥ 3.0) or Dask
- **Jupyter Notebook or JupyterLab**

### Python Dependencies

Install the necessary libraries with:
```bash
pip install requests pyspark pandas plotly geopandas geopy ipyleaflet