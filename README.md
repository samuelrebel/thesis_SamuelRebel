# Surface Water Pollution Prediction — Thesis Project

This repository contains all code used for spatial data processing, machine learning modelling, and result visualization for predicting global surface water pollutant concentrations using ensemble learning methods.

## Overview

The workflow consists of six main stages:

### 1. Predictor Preparation (`1_PredictorMerge.ipynb`)
- Load and merge static and monthly gridded predictor datasets.
- Output: a GeoDataFrame containing spatial predictors per month.

### 2. Observation Preprocessing (`2_Observations.ipynb`)
- Load surface water quality observations.
- Perform spatial joins to match observations with predictor values.

### 3. Model Training (`3_MonthlyModelTrain.ipynb`)
- Train Random Forest, XGBoost, and LightGBM models per pollutant and month.
- Supports four cross-validation strategies:
  - Random CV
  - GroupKFold by station
  - Leave-One-Country-Out (LOCO)
  - Leave-One-Basin-Out (LOBO)
- Output: predicted concentrations per location and model.

### 4. Feature Importance Analysis (`4_FeatureImportance`)
- Identify the top 5 most important predictors for each pollutant.
- Results are saved as barplots and a combined CSV summary.

### 5. Prediction Mapping (`5_VisualizationMaps`)
- Generate:
  - Annual average maps per pollutant (individual and grouped layouts),
  - Monthly maps for peak concentration periods,
  - A Spearman correlation heatmap across pollutants.

### 6. Performance Summarization (`6_VisualizationPerformance.ipynb`)
- Clean and summarize model performance (R² and RMSE).
- Create comparative tables across CV strategies.
- Identify seasonal trends (e.g. highest/lowest predicted months).

## Outputs

- Maps of predicted concentrations  
- Tables with model performance (R², RMSE)  
- Feature importance plots  
- Correlation heatmap of spatial patterns  

## Dependencies

Main packages:
- `pandas`, `geopandas`, `scikit-learn`, `xgboost`, `lightgbm`
- `matplotlib`, `seaborn`, `shapely`, `rasterio`, `cartopy`
## Author
Samuel Rebel, Utrecht University, Geoscience department.
