Data Preprocessing and Integration for Chesapeake Bay Project

Overview

This repository contains data preprocessing code for the Chesapeake Bay water quality analysis project. The objective of this project is to estimate river water quality in the Chesapeake Bay using machine learning models and multispectral satellite data. This specific code focuses on cleaning, normalizing, and integrating in-situ water quality measurements with satellite-derived data.

Contents

Files and Directories

	•	data_preprocess_code.ipynb: The main COLAB file containing the preprocessing code, including loading water quality data, data integration, and calculation of satellite-derived indices (NDVI and NDWI).
	•	raw_data/: Folder containing raw data files used for this project.
	•	MonitorEvent.csv: In-situ event monitoring data.
	•	Station.csv: Data file containing information about monitoring stations.
	•	WaterQuality.csv: Water quality data, including physical and chemical parameters.
	•	landsat_data/: Folder containing Landsat imagery bands used for calculating spectral indices.
	•	2022_04_B1.TIF: Coastal/Aerosol band.
	•	2021_12_B2.TIF: Blue band.
	•	2022_07_B3.TIF: Green band.
	•	2021_11_B4.TIF: Red band.
	•	2022_12_B5.TIF: Near-infrared (NIR) band.
	•	2021_04_B6.TIF: Short-wave infrared 1 (SWIR1) band.
	•	2021_08_B7.TIF: Short-wave infrared 2 (SWIR2) band.

Code Description

Main Steps in the Preprocessing Code

	1.	Loading Data:
	•	CSV files (MonitorEvent.csv, Station.csv, WaterQuality.csv) are loaded using pandas.
	•	Landsat imagery bands are loaded using rasterio.
	2.	Data Cleaning and Filtering:
	•	SampleDate column in WaterQuality.csv is converted to a datetime format for filtering.
	•	Data for the years 2021 and 2022 are filtered and combined for analysis.
	3.	Geospatial Data Handling:
	•	Latitude and Longitude data from the water quality dataset are used to create a GeoDataFrame for spatial analysis using geopandas.
	4.	Spectral Indices Calculation:
	•	NDVI (Normalized Difference Vegetation Index) and NDWI (Normalized Difference Water Index) are calculated from Landsat imagery bands using rasterio and skimage.
	5.	Visualization:
	•	Basic visualizations are provided for data distribution and geospatial plots using matplotlib.

Data Requirements and Setup

Raw Data

Place the raw data files (MonitorEvent.csv, Station.csv, WaterQuality.csv) in the raw_data/ directory. Ensure that Landsat imagery files are placed in the landsat_data/ directory.

Running the Code

To run the preprocessing code:
	1.	Ensure all required Python packages are installed.
  2.	Open and execute the code.

Notes

	•	The code is designed to run in a Google Colab environment.
	•	If using Jupyter Notebook, adjustments may be necessary for data paths and file access including downloading the raw data folder.
