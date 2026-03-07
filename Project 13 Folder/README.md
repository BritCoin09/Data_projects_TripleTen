📈 Time Series Forecasting: Sweet Lift Taxi Orders

📌 Project Overview

This project forecasts hourly taxi demand for the Sweet Lift Taxi company. The goal is to build a predictive model that estimates the number of taxi orders for the next hour so the company can optimize driver allocation and improve service efficiency. The target performance metric is RMSE ≤ 48 on the test set.

The project includes:

Resampling raw data to hourly frequency

Exploratory time‑series analysis

Feature engineering (lags, rolling means, calendar features)

Model training and comparison

Final model selection based on RMSE

📂 Dataset

The dataset is stored in taxi.csv and contains one column:

num_orders — the number of taxi orders in a given hour

The data spans March–August 2018 and includes 4,416 hourly observations.

🔍 Exploratory Analysis

Key findings from the analysis:

📈 Trend

Demand increases steadily from March through August.

Late summer shows the highest peaks.

⏰ Daily Seasonality

Highest demand around midnight

Lowest demand around 5–6 AM

Strong afternoon peak on weekdays

Weekends show higher late‑night activity

🔁 Autocorrelation

Strong autocorrelation at small lags

Clear peaks at lag 24 and lag 168, confirming daily and weekly cycles

Non‑stationary behavior with long memory

These patterns justify the use of lag, rolling, and calendar‑based features.

🛠 Feature Engineering

Features created:

lag_1, lag_24, lag_168

rolling_mean_24, rolling_mean_168

hour

day_of_week

is_weekend

Because rolling and lag features require up to 168 hours of history, early rows in each split were dropped after feature creation.

Note: In production, all features would be created before splitting to avoid shrinking the test set. For this project, the original TripleTen approach was followed for consistency.

🤖 Model Performance Summary

Here are the models trained and their RMSE scores:

- Linear Regression — RMSE: 36.29

Best performance

Captures linear seasonality extremely well

- Random Forest — RMSE: 43.48

Handles nonlinear patterns

Struggles with smooth seasonal structure

- Gradient Boosting — RMSE: 46.03

Better than RF

Still worse than Linear Regression

🏆 Final Model: Linear Regression

Lowest RMSE (36.29)

Meets the requirement of RMSE ≤ 48

Generalizes well

No visible bias in residual diagnostics

📊 Residual Diagnostics

Residuals fluctuate around zero with no trend

No signs of autocorrelation or systematic bias

Occasional spikes are expected due to real‑world variability (weather, events, etc.)

✅ Conclusion

The Linear Regression model is the best-performing model for forecasting hourly taxi demand. It effectively captures the strong linear seasonality present in the data and outperforms more complex tree‑based models.

This model provides Sweet Lift Taxi with a reliable forecasting tool that can:

Identify demand spikes

Improve driver scheduling

Reduce passenger wait times

Increase operational efficiency

To maintain accuracy, the model should be retrained regularly as new data becomes available.

📁 Files in This Folder

Project_13_clean.ipynb — Final notebook with full analysis

taxi.csv — Dataset

README.md — Project documentation