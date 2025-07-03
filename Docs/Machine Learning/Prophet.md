### 🔮 What is **Prophet**?

**Prophet** is an **open-source time series forecasting tool** developed by **Facebook** (now Meta).
It is designed to handle **daily observations with strong seasonality**, **holidays**, and **missing data** — and still produce **accurate forecasts**.

---

### 🧠 Simple Definition:

> **Prophet** builds forecasts using an **additive model**:
>
> **Forecast = Trend + Seasonality + Holidays + Error**

---

### ✅ Why Use Prophet?

| Advantage                    | Description                                              |
| ---------------------------- | -------------------------------------------------------- |
| **Easy to use**              | Simple API, even for non-experts                         |
| **Handles seasonality**      | Built-in yearly, weekly, daily patterns                  |
| **Holiday effects**          | You can add holidays (e.g., Diwali, Christmas) as inputs |
| **Missing data? No problem** | It automatically handles gaps in time                    |
| **Outlier resistant**        | Uses changepoint detection to handle sudden shifts       |

---

### 📦 When to Use Prophet?

* Daily/monthly sales or revenue data
* Web traffic or app usage prediction
* Financial time series (with trend/seasonality)
* Any business metric with strong time-based behavior

---

### 🔧 Prophet Model Components:

1. **Trend**: Long-term increase or decrease
2. **Seasonality**: Repeating patterns (e.g., weekly, yearly)
3. **Holidays**: Custom events that cause spikes/dips
4. **Error**: Random fluctuations

---

### 🐍 Python Example:

```python
from prophet import Prophet
import pandas as pd

# Create a dataframe with 'ds' (date) and 'y' (value)
df = pd.DataFrame({
    'ds': pd.date_range(start='2023-01-01', periods=30, freq='D'),
    'y': [112, 118, 130, 125, 140, 145, 150, 148, 136, 133,
          137, 139, 150, 155, 160, 162, 167, 169, 172, 175,
          178, 180, 182, 183, 185, 187, 190, 193, 195, 198]
})

# Fit the model
model = Prophet()
model.fit(df)

# Make future dataframe and forecast
future = model.make_future_dataframe(periods=10)  # Forecast next 10 days
forecast = model.predict(future)

# Plot forecast
model.plot(forecast)
```

---

### 📊 Output Columns from `forecast`:

| Column       | Description                        |
| ------------ | ---------------------------------- |
| `ds`         | Date                               |
| `yhat`       | Forecasted value                   |
| `yhat_lower` | Lower bound of prediction interval |
| `yhat_upper` | Upper bound of prediction interval |
| `trend`      | Estimated trend                    |
| `weekly`     | Weekly seasonality (if present)    |
| `yearly`     | Yearly seasonality (if present)    |

---

### 📌 Common Parameters:

* `daily_seasonality=True` – if daily patterns exist
* `seasonality_mode='additive'` or `'multiplicative'`
* `holidays` – custom holiday dataframe
* `changepoint_prior_scale` – flexibility of trend changes

---

### ✅ Pros:

* Great for **business forecasting**
* Minimal data preprocessing
* Automatically **detects changepoints**
* Visual diagnostics included

### ❌ Cons:

* Not ideal for **very short time series**
* May underperform compared to deep learning on **very complex** data
* Assumes future will look like past (doesn’t handle sudden shifts well without tuning)

---

### 🔁 Prophet vs ARIMA:

| Feature       | Prophet                    | ARIMA                    |
| ------------- | -------------------------- | ------------------------ |
| Seasonality   | Built-in                   | Needs SARIMA             |
| Missing Data  | Handles gracefully         | Needs interpolation      |
| Trend Changes | Automatic detection        | Manual differencing      |
| Interface     | High-level & user-friendly | Lower-level, statistical |
