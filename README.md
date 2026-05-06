# Bike Sharing Demand Prediction

Benchmarking SVM, GBM, and XGBoost to predict hourly bike rental demand using the Bike Sharing dataset (17,379 records).

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
17,379 hourly records with weather and temporal features

| Feature | Description |
|---------|-------------|
| hr | Hour of day (0-23) — strongest demand predictor |
| temp / atemp | Normalized temperature and feeling temperature |
| hum | Normalized humidity |
| windspeed | Normalized wind speed |
| season | Spring / Summer / Fall / Winter |
| weathersit | Weather condition (1: Clear → 4: Heavy Rain/Snow) |
| cnt | Target variable — total hourly bike rentals |

## Data Preprocessing
- **Data Cleaning** — handled missing values in temperature, humidity, and windspeed using KNN Imputation (k=5)
- **One-hot encoding** for categorical variables (season, month, hour, weekday, weather condition)

## Business Insights

- **Time-of-day dominates demand** — evening peaks (hr_17, hr_18) and morning commute (hr_8) are the highest-demand periods
- **Weather plays a secondary role** — temperature and humidity influence demand but are less critical than hour of day
- **1–5 AM is the optimal maintenance window** — extremely low demand makes it ideal for centralized bike maintenance and charging

## Recommendations

1. **Elastic Rebalancing Strategy** — use XGBoost hourly forecasts to redistribute bikes before rush periods and prevent stockouts
2. **Strategic Fleet Inventory Management** — maintain slightly higher inventory during comfortable non-peak hours to buffer demand surges
