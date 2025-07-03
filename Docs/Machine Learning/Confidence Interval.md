### 🎯 What is a **Confidence Interval (CI)?**

A **confidence interval** is a **range of values**, derived from sample data, that is likely to contain the **true population parameter** (like a mean or proportion) with a certain **level of confidence**.

---

### 🧠 Simple Definition:

> A 95% confidence interval means:
> “We are 95% confident that the **true value** lies **within this range**.”

---

### 📦 Example:

You sample 100 people and find the **average height = 170 cm**, with a **95% CI = \[167, 173]**.

➡ This means:
**“We are 95% confident that the true average height of the population is between 167 cm and 173 cm.”**

---

### 🧮 Confidence Interval Formula (for population mean):

$$
\text{CI} = \bar{x} \pm z^* \left( \frac{s}{\sqrt{n}} \right)
$$

Where:

* $\bar{x}$: sample mean
* $s$: sample standard deviation
* $n$: sample size
* $z^*$: z-score corresponding to confidence level (e.g., 1.96 for 95%)

---

### 🔢 Common Confidence Levels:

| Confidence Level | z-score ($z^*$) |
| ---------------- | --------------- |
| 90%              | 1.645           |
| 95%              | 1.96            |
| 99%              | 2.576           |

---

### 📉 Interpretation:

| Wider CI                    | Narrower CI                 |
| --------------------------- | --------------------------- |
| More confidence (e.g., 99%) | Less confidence (e.g., 90%) |
| Less precise estimate       | More precise estimate       |

---

### 🐍 Python Example:

```python
import numpy as np
import scipy.stats as stats

# Sample data
data = [170, 172, 168, 171, 169]
mean = np.mean(data)
sem = stats.sem(data)  # Standard error of the mean

# 95% CI
conf_interval = stats.t.interval(0.95, df=len(data)-1, loc=mean, scale=sem)
print("95% Confidence Interval:", conf_interval)
```

---

### ✅ Key Points:

* CI gives a **range**, not a single estimate
* Wider intervals → **more uncertainty**
* CIs apply to **population parameters**, not individuals
* Increasing sample size → **narrower CI**

---

### ❌ Misconceptions:

| Misconception                                     | Truth                                                                  |
| ------------------------------------------------- | ---------------------------------------------------------------------- |
| “There’s a 95% chance the parameter is in the CI” | ❌ Incorrect — The CI either **does or doesn’t** contain the true value |
| “CI gives range for individual values”            | ❌ CI is for **population mean**, not individual data points            |
