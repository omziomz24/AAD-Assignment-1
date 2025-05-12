# ACTL30008 Assignment 1: Predicting Housing Prices with MLR

## Overview
This repository contains the code and report for AAD Assignment 1, where we build, refine, and evaluate a multiple linear regression (MLR) model to predict median housing prices in California block groups.

## Data
- **Assignt1_data.csv**: Training dataset of 18,640 block groups with 10 variables (including `id`, `longitude`, `latitude`, `housingMedianAge`, `aveRooms`, `aveBedrooms`, `population`, `medianIncome`, `medianHouseValue`, `oceanProximity`) :contentReference[oaicite:0]{index=0}:contentReference[oaicite:1]{index=1}
- **Assignt1_test_full.csv**: Test dataset of 1,983 block groups for the final prediction competition :contentReference[oaicite:2]{index=2}:contentReference[oaicite:3]{index=3}

## Methods
### Descriptive Analysis
- Loaded and cleaned data; removed missing values.
- Conducted numerical summaries and graphical exploration (histograms, correlation matrix, geospatial heatmap, scatterplots, boxplots) to identify data censoring and reveal key relationships :contentReference[oaicite:4]{index=4}:contentReference[oaicite:5]{index=5}

### Multiple Linear Regression (Initial Model)
- Fitted an initial MLR using all relevant predictors (excluding `id`).
- Performed F-tests for overall model significance and t-tests for individual coefficients.
- Diagnosed potential issues: heteroscedasticity, non-normality, outliers, high-leverage points, and multicollinearity :contentReference[oaicite:6]{index=6}:contentReference[oaicite:7]{index=7}

### Model Improvements
- Engineered new features: `bedroomsPerRoom`, `incomePerRoom`, Euclidean distances and directional components to Los Angeles and San Francisco, `cityProximityScore`, and `distToCenter`.
- Incorporated interaction terms and nonlinear transformations based on diagnostic findings and domain insight.
- Selected the final feature set via best-subset selection with k-fold cross-validation :contentReference[oaicite:8]{index=8}:contentReference[oaicite:9]{index=9}

### Model Performance
- Calculated training MSE for both initial and final models.
- Estimated test error via 80–20 validation split, 5-fold cross-validation, and LOOCV.
- Demonstrated improved predictive performance of the final model :contentReference[oaicite:10]{index=10}:contentReference[oaicite:11]{index=11}

### Prediction Competition
- Generated predictions on `Assignt1_test_full.csv` using the final model.
- Computed test MSE and ranked performance in the class competition :contentReference[oaicite:12]{index=12}
