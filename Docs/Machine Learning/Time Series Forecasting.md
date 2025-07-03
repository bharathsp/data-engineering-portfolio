### ⏳ What is **Time Series Forecasting**?

**Time Series Forecasting** is the process of using **historical data points collected over time** to **predict future values**.

---

### 🧠 Simple Definition:

> It’s like using past sales, temperatures, or stock prices to predict what will happen **next**.

---

### 📦 What is a Time Series?

A **time series** is a sequence of observations recorded at **regular time intervals**:

* Daily (e.g., stock prices)
* Monthly (e.g., electricity bills)
* Yearly (e.g., population growth)

🗓️ Example:

```
Date       | Sales
-----------|------
2023-01-01 | 150
2023-01-02 | 160
2023-01-03 | 145
```

---

### 📊 Goal of Forecasting:

To model patterns like:

* **Trend** (long-term upward or downward movement)
* **Seasonality** (repeating short-term cycles)
* **Cyclicality** (irregular longer-term changes)
* **Noise** (random fluctuations)

---

### 🔮 Common Use Cases:

* Stock price prediction
* Demand forecasting
* Weather forecasting
* Website traffic prediction
* Inventory management

---

### 🔧 Common Techniques:

| Type              | Method                               | When to Use                                     |
| ----------------- | ------------------------------------ | ----------------------------------------------- |
| **Statistical**   | ARIMA, SARIMA, Exponential Smoothing | Small to medium datasets, interpretable results |
| **ML-Based**      | XGBoost, Random Forest, LSTM (RNNs)  | Large/complex data, nonlinear patterns          |
| **Deep Learning** | LSTM, GRU, Transformer models        | Sequence-dependent and large datasets           |
| **Hybrid**        | Combined methods                     | Mix of accuracy and interpretability            |

---

### 🐍 Simple Python Example (Using ARIMA):

```python
import pandas as pd
from statsmodels.tsa.arima.model import ARIMA
import matplotlib.pyplot as plt

# Sample time series data
data = pd.Series([112, 118, 132, 129, 121, 135, 148, 148, 136, 119], 
                 index=pd.date_range(start='2023-01', periods=10, freq='M'))

# Fit ARIMA model
model = ARIMA(data, order=(1, 1, 1))  # (p, d, q)
model_fit = model.fit()

# Forecast next 3 points
forecast = model_fit.forecast(steps=3)
print("Forecast:", forecast)

# Plot
data.plot(label="History")
forecast.plot(label="Forecast", legend=True)
plt.show()
```

---

### ✅ Benefits:

* Helps plan for the future
* Data-driven decision making
* Detects trends and seasonality

### ❌ Challenges:

* Sensitive to **missing data** and **outliers**
* Assumes **stationarity** (constant mean/variance) in many models
* Forecasts become less reliable the further out you go

---

### 📈 Key Concepts in Time Series:

* **Lag**: Past values (t-1, t-2, ...)
* **Rolling average**: Smooths data
* **Differencing**: Makes non-stationary data stationary
* **Autocorrelation**: Relationship between time-lagged variables
