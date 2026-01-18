
# Walmart Sales Forecasting: From Baseline to 94.5% Accuracy

## 📌 Project Overview

This project focuses on predicting weekly sales for 45 Walmart stores using historical data. The primary challenge was overcoming low initial correlations between sales and external factors like CPI and Unemployment. Through extensive **feature engineering** and **model optimization**, the project achieved a high-performance predictive system.

## 🚀 The Transformation Journey

The project evolved through three distinct phases, significantly reducing the Mean Absolute Error (MAE) by over **$400,000**.

| Phase | Action Taken |  Score | Average Error (MAE) |
| --- | --- | --- | --- |
| **Initial** | Raw Data + Linear Regression | **0.04** | ~$470,000 |
| **Mid-Stage** | Added Store IDs & Basic Engineering | **0.92** | ~$80,000 |
| **Final Champion** | **Tuned CatBoost + Lagged Features** | **0.945** | **$72,474** |

## 🛠️ Key Feature Engineering (The "Secret Sauce")

The massive jump in accuracy was driven by the creation of custom features designed to capture consumer behavior and economic stress:

* **Eco_Pain_Index**: An interaction term multiplying CPI and Unemployment to better represent the combined economic pressure on shoppers.
* **Last_Week_Sales (Lagged)**: Captures store-specific momentum, recognizing that the best predictor of today's sales is often what happened last week.
* **Is_Holiday_Season**: A strategic date feature covering November and December, capturing the full retail surge beyond just specific holiday dates.
* **Fuel_Price_Change**: Measures price volatility as a consumer "shock" indicator rather than just the raw fuel price.

## 📊 Model Performance Comparison

We benchmarked several algorithms to find the most robust predictor. While all models benefited from the engineered features, **CatBoost** emerged as the champion due to its superior handling of categorical store data.

| Model | R2-Score | MAE |
| --- | --- | --- |
| **CatBoostRegression** | **0.9452** | **$72,474** |
| **LinearRegression** | 0.9418 | $80,405 |
| **RandomForestRegression** | 0.9365 | $78,346 |
| **XGBoostRegression** | 0.9335 | $76,731 |
| **KNNRegression** | 0.9116 | $95,120 |

## 🔍 Key Insights & Feature Importance

The **Feature Importance** analysis confirms that store momentum and economic indicators were the primary drivers of the model's success.

* **Momentum is King**: `Last_Week_Sales` was the single most influential predictor.
* **Robustness**: The high score of Linear Regression (0.94) proves that the engineered features have successfully turned a complex non-linear problem into a highly predictable one.
* **Holiday Accuracy**: The model tracks seasonal peaks effectively, though deep-dive analysis shows the highest errors occur during the volatile "Post-Holiday Slump" in late December.

## 🏁 Conclusion

The project successfully delivered a highly accurate () forecasting tool. By focusing on **Domain-Specific Feature Engineering** rather than just algorithmic complexity, the model provides actionable insights into how economic shifts and seasonal trends impact Walmart's bottom line.

