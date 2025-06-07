# Walmart Sales Forecasting Using ARIMA

## 📝 Project Overview

This project tackles the real-world challenge of **forecasting weekly sales** across different **departments and stores of Walmart**, inspired by the Kaggle competition “Walmart Recruiting: Store Sales Forecasting.” Due to the seasonal nature of retail—where critical periods like holidays occur only once a year—predicting sales requires strategic handling of limited historical data.

The primary objective of this project is to **develop time series forecasting models using ARIMA** to predict future sales, while understanding the impact of holidays and markdown events.

---

## 📂 Dataset

The dataset comprises four CSV files:

1. `walmart_train.csv`: Historical sales data with weekly sales figures for each department-store combination.
2. `walmart_test.csv`: Test data for making future sales predictions.
3. `walmart_stores.csv`: Metadata about store types and sizes.
4. `walmart_features.csv`: Additional features such as temperature, fuel price, CPI, unemployment rate, and various markdowns. These are known to affect sales.

Key columns include:
- `Store`, `Dept`, `Date`, `Weekly_Sales`
- `IsHoliday`, `MarkDown1-5`, `CPI`, `Unemployment`, `Type`, `Size`

---

## 🛠 Tools and Libraries Used

- **Python 3**
- **Pandas & NumPy** for data manipulation
- **Matplotlib & Seaborn** for static visualizations
- **Plotly** for interactive visualizations
- **Statsmodels** for ARIMA modeling and seasonal decomposition
- **scikit-learn** for encoding and data preprocessing

---

## 🔍 Key Steps & Methodology

1. **Exploratory Data Analysis (EDA):**
   - Identified missing values and distribution of sales.
   - Analyzed trends by department, store, and over time.

2. **Feature Engineering:**
   - Created a combined `Store_Dept` key for granular forecasting.
   - Extracted `Month` and `Year` from date.
   - Aggregated markdown values into a `Total_MarkDown` feature.
   - Created lag features to capture weekly trends (`Lag1`, `Lag2`).

3. **Encoding and Merging:**
   - One-hot encoded `Store Type`.
   - Merged datasets to align store, features, and sales for a unified model input.

4. **ARIMA Modeling:**
   - Applied the **ARIMA** model for univariate forecasting of weekly sales.
   - Seasonal Decomposition was performed to understand trend, seasonality, and residuals.

---

## 📈 Key Insights

- **Seasonality is significant** in Walmart sales data, especially around major holidays like Thanksgiving and Christmas.
- **Markdowns play a major role** in increasing sales, but their effects vary by department and store type.
- Certain store types consistently outperform others, suggesting location and store size/type are crucial factors.
- **Lagged sales features** proved useful in capturing short-term dependencies.

---

## 💡 Recommendations

1. **Optimize holiday markdown strategies** as they significantly impact sales spikes.
2. Focus forecasting efforts more precisely at the **department level**, rather than aggregated store-level predictions.
3. Consider hybrid models that incorporate both **ARIMA and machine learning methods** for improved accuracy.
4. Include more **exogenous variables** like regional events or promotions in future modeling.

---

## 📁 Folder Structure

