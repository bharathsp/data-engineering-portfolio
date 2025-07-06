### 📈 What is **ARIMA**?

**ARIMA** stands for **AutoRegressive Integrated Moving Average**.
It is a powerful **statistical model** used for **time series forecasting** when data shows **patterns over time** but **no strong seasonal component**.

---

### 🔍 Breakdown of ARIMA:

ARIMA(p, d, q) has **3 components**:

| Component                   | Meaning                                                    |
| --------------------------- | ---------------------------------------------------------- |
| **AR (p)** – AutoRegressive | Uses **past values** to predict the current value          |
| **I (d)** – Integrated      | Makes the data **stationary** by differencing              |
| **MA (q)** – Moving Average | Uses **past forecast errors** to predict the current value |

> Example: ARIMA(1,1,1)
> ➝ Uses 1 lag of past values (AR), 1 differencing (I), and 1 lag of forecast error (MA)

---

### 📦 When to Use ARIMA?

Use ARIMA when:

* Your time series has **trend** but **no seasonality**
* The data becomes **stationary after differencing**
* You want **explainable forecasts**

---

### 📊 Stationary Data?

A **stationary time series** has:

* Constant **mean** over time
* Constant **variance**
* No seasonality or trend

If your data isn’t stationary → apply **differencing** (`d > 0` in ARIMA).

---

### 🧮 ARIMA Model Equation:

$$
Y_t = c + \phi_1 Y_{t-1} + \cdots + \phi_p Y_{t-p} + \theta_1 \epsilon_{t-1} + \cdots + \theta_q \epsilon_{t-q} + \epsilon_t
$$

Where:

* $Y_t$: value at time t
* $\phi$: AR coefficients
* $\theta$: MA coefficients
* $\epsilon$: error terms (residuals)

---

### 🐍 ARIMA in Python Example:

```python
import pandas as pd
from statsmodels.tsa.arima.model import ARIMA
import matplotlib.pyplot as plt

# Sample data
data = pd.Series([112, 118, 132, 129, 121, 135, 148, 148, 136, 119], 
                 index=pd.date_range(start='2023-01', periods=10, freq='M'))

# Fit ARIMA(p=1, d=1, q=1)
model = ARIMA(data, order=(1, 1, 1))
model_fit = model.fit()

# Forecast next 3 periods
forecast = model_fit.forecast(steps=3)
print("Forecast:", forecast)

# Plot
data.plot(label="Actual")
forecast.plot(label="Forecast", legend=True)
plt.title("ARIMA Forecast")
plt.show()
```

---

### ✅ Advantages:

* Great for **short-term forecasting**
* Can model **non-stationary** data
* Works well on **univariate time series**

### ❌ Limitations:

* Doesn't handle **seasonality** well (use **SARIMA** instead)
* Requires **stationarity**
* Can be complex to **tune p, d, q**

---

### 📦 ARIMA vs SARIMA?

| Model      | Handles Seasonality? | Use When                 |
| ---------- | -------------------- | ------------------------ |
| **ARIMA**  | ❌ No                 | Trend but no seasonality |
| **SARIMA** | ✅ Yes                | Data has seasonal cycles |
