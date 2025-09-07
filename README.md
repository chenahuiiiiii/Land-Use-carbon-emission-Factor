# Land-Use-carbon-emission-Factor
Code for land use carbon emission driving factor contribution analysis, including raster combination, random point extraction, XGBoost-SHAP interaction analysis, and Bootstrap-based heterogeneity evaluation. Part of the paper on SBM-DEA and carbon efficiency in Shanxi, China.
# Land-Use Carbon Emission Drivers Analysis (Shanxi Province)
This repository contains the core scripts used in our study on the drivers of land-use carbon emissions (LUCE) and efficiency analysis in Shanxi Province, China.  
The workflow integrates spatial data processing, econometric modeling, and machine learning interpretation.  
## Repository Structure
- **1_CombineFigure.py**  
  - Function: Merge raster layers of driving factors (e.g., GDP, population, land use, NDVI) into a single composite map.  
  - Output: Combined raster for factor extraction.  
- **2_RandomPointExtraction.py**  
  - Function: Generate 1200 random sampling points across the study area.  
  - Each point records pixel coordinates and values from all driving-factor layers.  
  - Output: CSV file with random sample dataset.  
- **3_XGBoost_SHAP.py**  
  - Function: Train XGBoost model using extracted factor values and LUCE as the dependent variable.  
  - Apply SHAP values to interpret individual feature contributions and interactions.  
  - Output: SHAP summary plots and interaction effects.  
- **4_Bootstrap_CV.py**  
  - Function: Perform bootstrap resampling and k-fold cross-validation (k=5).  
  - Estimate R² distribution to assess robustness and heterogeneity.  
  - Output: Distribution plots and average model metrics.  
## Requirements
- Python 3.9+  
- Libraries: `numpy`, `pandas`, `geopandas`, `matplotlib`, `scikit-learn`, `xgboost`, `shap`, `pysal`  
Install dependencies:
```bash
pip install -r requirements.txt


## License
This project is licensed under the MIT License - you are free to use, modify, and distribute the code with proper attribution.
