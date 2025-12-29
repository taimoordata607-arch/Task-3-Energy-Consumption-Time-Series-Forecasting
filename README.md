# Energy Consumption Time Series Forecasting

## 📌 Project Objective
The objective of this project is to forecast short-term household energy usage (Global Active Power) by analyzing historical time-based patterns. This allows for better energy management and demand prediction.

---

## 📊 Project Summary
This project involves an end-to-end analysis of energy consumption data, moving from high-frequency (minute-level) raw data to a daily-aggregated forecasting model.

### 1. Data Preparation and Resampling
To ensure high data integrity and capture meaningful trends, the following steps were taken:
* **DateTime Indexing**: Combined 'Date' and 'Time' columns into a single DateTime index to establish chronological order.
* **Data Cleaning**: Handled non-numeric entries and filled gaps using forward-fill (`ffill`) and backward-fill (`bfill`) to ensure a continuous time series.
* **Resampling**: The original minute-level data was resampled to a **daily frequency** (calculating the mean kW), reducing noise and highlighting seasonal patterns.
* **Dataset Scope**: The processed data spans from December 2006 to December 2008.

### 2. Time-Series Analysis
* **Stationarity Check**: Performed the Augmented Dickey-Fuller (ADF) test to check if the series was stationary, a requirement for traditional models like ARIMA.
* **Decomposition**: Analyzed the series to identify underlying **trend**, **seasonality**, and **residuals**.

---

## 🤖 Model Performance Comparison
Three distinct forecasting approaches were implemented and compared to determine the most accurate model for predicting `Global_active_power`.

| Model | RMSE (Root Mean Squared Error) | MAE (Mean Absolute Error) |
| :--- | :--- | :--- |
| **ARIMA** | 0.4578 | 0.3541 |
| **Prophet** | 0.4468 | 0.3441 |
| **XGBoost** | **0.4284** | **0.3204** |

*Note: Lower values for RMSE and MAE indicate better performance. **XGBoost** emerged as the most accurate model in this study.*

---

## 📈 Key Findings
* **Model Accuracy**: The Machine Learning approach (**XGBoost**) outperformed the statistical (**ARIMA**) and additive (**Prophet**) models by better capturing non-linear relationships and complex patterns in the energy data.
* **Seasonality**: The data shows clear seasonal fluctuations in energy usage, which Prophet was particularly good at identifying, though XGBoost handled the residuals more effectively.
* **Volatility**: Energy consumption exhibits short-term spikes that traditional linear models struggle to predict perfectly, highlighting the value of ensemble learning.

---

## 🛠️ Tech Stack
* **Language**: Python
* **Forecasting Models**: 
    * `Statsmodels` (ARIMA)
    * `Prophet` (Facebook/Meta)
    * `XGBoost` (Gradient Boosting)
* **Data Science Tools**: `Pandas`, `NumPy`, `Scikit-Learn`, `Matplotlib`, `Seaborn`

---

## 🚀 How to Run
1.  **Clone the repo**:
    ```bash
    git clone <https://github.com/taimoordata607-arch/Task-3-Energy-Consumption-Time-Series-Forecasting>
    ```
2.  **Install dependencies**:
    ```bash
    pip install pandas numpy matplotlib seaborn statsmodels prophet xgboost scikit-learn
    ```
3.  **Run the script**:
    ```bash
    python task_3_energy_consumption_time_series_forecasting.py
    ```
