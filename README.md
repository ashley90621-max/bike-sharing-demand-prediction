# Bike Sharing Demand Prediction

Benchmarking SVM, GBM, and XGBoost to predict hourly bike rental demand using the UCI Bike Sharing dataset (17,379 records).

## Model Results

| Model | RMSE ↓ | R² ↑ |
|-------|--------|------|
| SVM | 123.66 | 0.517 |
| GBM | 81.44 | 0.791 |
| **XGBoost** | **74.75** | **0.823** |

✅ XGBoost achieved the lowest RMSE and highest R², outperforming both SVM and GBM.

## Key Methods
- **KNN Imputation (k=5)** — handled missing values in temperature, humidity, and windspeed
- **Feature Engineering** — one-hot encoding for season, month, hour, weekday, and weather condition
- **Feature Importance Analysis** — identified key demand drivers for SVM, GBM and XGBoost
- **Model Evaluation** — compared models via RMSE (lower is better) and R² (higher is better)

## Tech Stack
Python · XGBoost · Scikit-learn · KNN Imputer · Pandas · Matplotlib · Seaborn

## Dataset
[Kaggle — Bike Sharing Dataset](https://www.kaggle.com/datasets/lakshmi25npathi/bike-sharing-dataset) — hourly bike rentals with weather and temporal features

## Data Preprocessing
- **Data Cleaning** — handled missing values in temperature, humidity, and windspeed using KNN Imputation (k=5)
- **One-hot encoding** for categorical variables (season, month, hour, weekday, weather condition)
