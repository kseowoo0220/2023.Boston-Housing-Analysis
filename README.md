# Boston Housing Price Analysis

This project analyzes the **determinants of Boston housing prices** using regression modeling.  
The aim is to identify key factors that influence housing prices and to develop a robust predictive model.

## Overview
Boston has become one of the most expensive U.S. cities for renters.  
This study investigates which demographic, geographic, and environmental factors drive housing prices, applying **exploratory data analysis, model diagnostics, transformations, and model selection** to improve predictive accuracy.

## Data
- **Dataset:** Boston Housing dataset (n = 506)  
- **Outcome:** Median value of owner-occupied homes (MEDV)  
- **Predictors:** 13 covariates, including:  
  - CRIM (per capita crime rate)  
  - RM (average number of rooms per dwelling)  
  - TAX (property-tax rate)  
  - RAD (index of accessibility to radial highways)  
  - LSTAT (proportion of lower status population)  
  - NOX, PTRATIO, AGE, DIS, etc.  

## Methods
1. **Exploratory Data Analysis (EDA)**  
   - Distribution checks and correlation analysis  
   - Identified skewed variables (AGE, DIS, LSTAT) and multicollinearity (RAD, TAX)  

2. **Full Model**  
   - Linear regression with all predictors  
   - Adjusted R² = 0.7338  
   - Violations found in linearity, homogeneity, and normality assumptions  

3. **Diagnostics & Transformations**  
   - Box-Cox transformation → log(MEDV)  
   - Removed outlier (observation 365 with extreme RM value)  
   - Addressed collinearity: removed TAX, reduced VIF of RAD  

4. **Model Selection**  
   - Backward elimination (α = 0.05)  
   - Removed ZN, INDUS, AGE  
   - Final reduced model fitted  

## Results
- **New Model:**  

![New Model Equation](./assets//Users/kseowoo/Library/CloudStorage/OneDrive-Personal/resume project data and code/boston_new_model_equation.svg)


- **Performance:** Adjusted R² = **0.796** (improved from 0.734 in full model)  
- **Significant predictors:** CRIM, CHAS, NOX, RM, log(DIS), RAD, PTRATIO, B, LSTAT  
- **Interpretation:**  
  - Positive associations: proximity to Charles River (CHAS), more rooms (RM), better accessibility (RAD), population homogeneity (B)  
  - Negative associations: higher crime, air pollution, longer commuting distances, higher tax/pupil-teacher ratio, higher proportion of lower status population  

## Key Insights
- Housing prices in Boston are strongly influenced by **location, housing quality, and socioeconomic factors**.  
- Model improvements through transformation and feature selection increased accuracy and interpretability.  
- Limitations: Dataset reflects 1970s housing data; results may not fully generalize to current Boston housing markets.  
- Future work: Explore **polynomial regression** or more recent datasets for better predictions.  

---
