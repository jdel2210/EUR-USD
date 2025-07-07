# 💱 EUR/USD Exchange Rate Forecasting with Machine Learning

This project uses historical Euro/US Dollar (EUR/USD) exchange rate data and technical indicators to forecast both the **direction** and **value** of future prices using supervised machine learning models. The goal is to demonstrate the use of classification and regression techniques to predict exchange rate behavior.

---

## 📊 Data Overview

- **Source**: European Central Bank time series.
- **Key Column**:  
  `Euro/US dollar (EXR.D.USD.EUR.SP00.A)` — daily EUR/USD exchange rate.

- **Date Range**: 1999 to 2025 (varies depending on CSV).
- **Date Column**: `TIME PERIOD` or `DATE`.

---

## 🧠 Features Engineered

| Feature     | Description                                      |
|-------------|--------------------------------------------------|
| `Return`    | Daily % change in EUR/USD                        |
| `Lag1`/`Lag2` | 1-day & 2-day lagged returns                   |
| `Volatility`| Rolling 5-day return standard deviation          |
| `SMA_50`    | 50-day simple moving average                     |
| `SMA_200`   | 200-day simple moving average                    |
| `RSI`       | Relative Strength Index (14-day)                 |
| `MACD`      | MACD line (12-26 EMA)                            |
| `MACD_signal` | MACD signal line (9 EMA of MACD)              |
| `Momentum`  | Price difference over 10 days                    |

---

## 🎯 Targets

- **Classification Target**:  
  `Target = 1 if next-day return > 0 else 0`

- **Regression Target**:  
  `Target = EURUSD shifted by -1 to -3 days`  
  (i.e., future exchange rate)

---

## 🧪 Models Used

### 🔹 Classification

- **Model**: `RandomForestClassifier`
- **Metrics**:
  - Accuracy
  - Precision, Recall, F1-score
  - Confusion Matrix

### 🔹 Regression

- **Model**: `RandomForestRegressor`
- **Metrics**:
  - Mean Squared Error (MSE)
  - Visual plot of actual vs predicted prices

---

## 📈 Visualizations

- **Feature Importances** — Barplot to show which features matter most.
- **Cumulative Returns** — Strategy vs Buy & Hold.
- **Predicted vs Actual** — Comparison plot for regression predictions.
