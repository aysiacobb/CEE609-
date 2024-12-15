# **Chlorophyll-a Prediction Using In-Situ and Satellite Data**

This readme is associated with  the model_training_609_chesapeake.ipynb and contains code and data for predicting chlorophyll-a (CHLA) levels in the Chesapeake Bay watershed using a Random Forest regression model. The project integrates in-situ water quality measurements and satellite-derived Landsat data to improve prediction  accuracy.

## **Workflow Overview:**

### 1. Data Preprocessing
The project begins with building off of the preprocessed data and then further cleaning and restructuring of the datasets:

In-Situ Data:

* Columns include water quality parameters such as PH, TN, TP, WTEMP, DO, and TURB_NTU.
  
* In-situ data is reshaped using the Parameter column, converting it into separate features (e.g., CHLA, KD, TN, etc.).
  
Satellite Data:

* Landsat bands (1–7) and indices (NDVI, NDWI) are derived from .tif files. NDVI and NDWI are manually calculated using the Landsat bands.
 
*	Satellite data is captured at the locations of the in-situ measurements.

### 2. Feature Extraction
 
*	Extract raster values from Landsat .tif files for Bands 1–7, NDVI, and NDWI.

* Use GDAL and rasterio to efficiently map satellite-derived values to in-situ points.

### 3. Model Training
The workflow involves training two Random Forest models:
	1. In-Situ Model: Trained using only in-situ measurements as predictors.
	2. Integrated Model: Trained using both in-situ measurements and satellite-derived data.

### 4. Model Evaluation
The models are evaluated using:

*	Mean Absolute Error (MAE)

*	Root Mean Square Error (RMSE)

*	R² Score

The integrated model of the satellite and in-situ measurements demonstrated an improved performance based on the evaluation parameters. 

### 5. Feature Importance Analysis

The feature importances for each model are visualized to understand which predictors contribute most to CHLA predictions for both the models .

## **Inputs and Outputs of Project Directory** 

Inputs 
1. In-situ measurements
2. LANDSAT raster files
3. Extracted raster values for in-situ points
4. Predictors: Bands 1-7 and in-situ parameters
5. n-situ and combined measurements
6. Scatterplot of actual vs predicted CHLA values

Outputs 
1. Final dataset combining the in-situ and satellite data
2. Model predictions for CHLA
3. Normalized predictors 
4. Trained Random Forest models for only in-situ and then in-situ and satellite data combined
5. MAE, RMSE, R2
6. Feature Importance plots

## **Key Results**
1. Model with In-Situ Data Only:
 
*	MAE: 1.3178
 
*	RMSE: 3.4251
 
*	R²: 0.5291
 
	2.	Model with In-Situ + Satellite Data:
 
*	MAE: 1.2161
 
*	RMSE: 3.1372
 
*	R²: 0.7945
 
Conclusion: Incorporating satellite-derived data significantly improves predictive accuracy for chlorophyll-a levels.

## Acknowledgments of Sources for Data
This project uses:
*	Landsat Data: Courtesy of NASA and USGS.
 
*	In-Situ Water Quality Data: Sourced from the Chesapeake Bay Monitoring Program.
