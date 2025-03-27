# Global Weather and Air Quality Analysis

## Overview

This project analyzes the `GlobalWeatherRepository.csv` dataset, containing weather and air quality data for global regions during May 2024 and March 2025. The goal is to clean and preprocess the data, explore climate patterns, investigate air quality relationships, and forecast temperature using machine learning models. This work aligns with the PM Accelerator’s mission to empower future product managers with data-driven insights and AI skills.

## Objectives

- Clean and preprocess the dataset for analysis.
- Perform Exploratory Data Analysis (EDA) on temperature and precipitation.
- Analyze climate patterns (temperature and wind speed) by continent and time period.
- Investigate the relationship between air quality (PM2.5) and weather parameters.
- Forecast temperature using Linear Regression, SVR, and Random Forest models.

## Dataset

- **File**: `GlobalWeatherRepository.csv`
- **Columns**: 41, including `country`, `location_name`, `latitude`, `timezone`, `temperature_celsius`, `humidity`, `wind_mph`, `precip_mm`, `condition_text`, and `air_quality_PM2.5`.
- **Time Periods**: May 2024 and March 2025.

## Methodology

1. **Data Cleaning**:

   - Handled missing values using `SimpleImputer` (median for numeric, most frequent for categorical).
   - Clipped outliers using the IQR method.
   - Scaled numeric features to z-scores using `StandardScaler`.
   - Saved cleaned data as `GlobalWeatherRepository_cleaned.csv`.

2. **Exploratory Data Analysis (EDA)**:

   - Visualized temperature and precipitation distributions, temporal trends, latitudinal patterns, and weather condition impacts.
   - Generated a correlation heatmap for key weather parameters.

3. **Climate Pattern Analysis**:

   - Extracted continents from `timezone` and categorized data into May 2024 and March 2025.
   - Analyzed scaled temperature and wind speed trends by continent and time period.

4. **Air Quality Analysis**:

   - Explored correlations between PM2.5 and weather parameters.
   - Analyzed PM2.5 levels by weather condition and continent.

5. **Predictive Modeling**:
   - Trained Linear Regression, SVR, and Random Forest models to predict `temperature_celsius`.
   - Evaluated models using MSE, MAE, and R² score.

## Key Findings

- **EDA**: Temperature (mean 22.14°C) follows latitudinal and seasonal patterns, with Africa and Asia warmer, and North America and Europe cooler in March 2025. Precipitation is sparse but reduces PM2.5 levels.
- **Climate Patterns**: North America and Antarctic show higher wind speeds in March 2025, potentially improving air quality.
- **Air Quality**: Mist has the highest PM2.5 (1.75 µg/m³), while higher wind speeds and precipitation reduce pollution.
- **Modeling**: Random Forest outperformed other models in temperature forecasting (R² = 0.86, MAE = 0.26°C, MSE = 0.16°C²), achieving an 83% lower MSE and 65% lower MAE than Linear Regression.

## Requirements

- Python 3.8+
- Libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

Install dependencies:

```bash
pip install -r requirements.txt
```
