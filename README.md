Land-Use-carbon-emission-Factor

Code for land-use carbon emission driving factor contribution analysis, including raster combination, random point extraction, XGBoost-SHAP interaction analysis, Bootstrap-based heterogeneity evaluation, and DEA/SFA-based carbon efficiency analysis. Part of the paper on SBM-DEA and carbon efficiency in Shanxi, China.

Land-Use Carbon Emission Drivers Analysis (Shanxi Province)

This repository contains the core scripts and datasets used in our study on the drivers of land-use carbon emissions (LUCE) and efficiency analysis in Shanxi Province, China.
The workflow integrates spatial data processing, econometric modeling, machine learning interpretation, and DEA/SFA efficiency estimation.

Repository Structure
SBM-DEA/

Folder containing files related to SBM-DEA efficiency analysis using MaxDEA.
Includes model configuration and processed data for replication. Detailed model settings (orientation, returns to scale, handling of undesirable outputs, etc.) are documented for reproducibility.

SFA/

Folder containing files related to Stochastic Frontier Analysis (SFA) using FRONTIER 4.1.

SFAins.txt — Complete instruction file for SFA estimation.

SFADATA.txt — Data file corresponding to the SFA model.
Any researcher can download FRONTIER 4.1 and use these files to fully replicate all estimation results and technical efficiency scores.

Python Scripts

Bootstrap_CV.py
Function: Perform bootstrap resampling and 5-fold cross-validation to assess model robustness and heterogeneity.
Output: Distribution plots and average model metrics.

CombineFigure.py
Function: Merge raster layers of driving factors (e.g., GDP, population, land use, NDVI) into a single composite raster.
Output: Combined raster for factor extraction.

RandomPointExtraction.py
Function: Generate 1200 random sampling points across the study area. Each point records pixel coordinates and values from all driving-factor layers.
Output: CSV file with random sample dataset (random_points_with_coordinates.csv).

XGBoost_SHAP.py
Function: Train XGBoost model using extracted factor values and LUCE as the dependent variable. Apply SHAP values to interpret individual feature contributions and interactions.
Output: SHAP summary plots and interaction effect visualizations.

Data Files

original_inputs.csv / original_inputs.xlsx — Raw input data including land-use areas, environmental variables, desired and undesired outputs for DEA/SFA.

processed_inputs.csv — Standardized and processed data ready for DEA/SFA and machine learning analysis.

spatial_diagnostics.csv — Results of spatial diagnostics (Moran's I, LM tests, etc.) for assessing spatial autocorrelation.

spatial_regions.png — Visualization of spatial regions or partitions used for cross-validation and analysis.

spatial_weights.csv — Row-standardized spatial weights matrix for spatial econometrics analysis.

Requirements

Python 3.9+

Libraries: numpy, pandas, geopandas, matplotlib, scikit-learn, xgboost, shap, pysal

Install dependencies:

pip install -r requirements.txt

License

This project is licensed under the MIT License. You are free to use, modify, and distribute the code with proper attribution.
