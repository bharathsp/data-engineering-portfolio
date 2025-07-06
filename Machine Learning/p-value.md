### 🧪 What is a **p-value**?

A **p-value** (probability value) is a **statistical metric** that helps you determine the **strength of evidence against the null hypothesis (H₀)** in a hypothesis test.

---

### 🎯 Simple Definition:

> The **p-value** is the **probability** of obtaining results **at least as extreme** as the observed results, **assuming the null hypothesis is true**.

---

### 🧠 Think of It Like This:

* A **small p-value** → evidence **against** the null hypothesis
* A **large p-value** → data is **consistent** with the null hypothesis

---

### ✅ p-value Interpretation Guide:

| p-value    | Interpretation                                |
| ---------- | --------------------------------------------- |
| **≤ 0.01** | Strong evidence against H₀ (Very significant) |
| **≤ 0.05** | Moderate evidence against H₀ (Significant)    |
| **> 0.05** | Weak evidence against H₀ (Not significant)    |

> If **p ≤ α** (e.g., 0.05) → **Reject H₀**
> If **p > α** → **Fail to reject H₀**

---

### 📚 Example:

You test whether a new drug lowers blood pressure.

* H₀: The drug has **no effect**
* H₁: The drug **does have an effect**
* You run a test and get **p = 0.03**

✔ Since 0.03 < 0.05, you **reject H₀** — the drug likely has an effect.

---

### 🐍 Python Example:

```python
from scipy.stats import ttest_1samp

data = [68, 70, 72, 69, 71]
t_stat, p_val = ttest_1samp(data, 70)

print("p-value:", p_val)
```

---

### ⚠️ Common Misconceptions:

| Misconception                                   | Truth                                                                            |
| ----------------------------------------------- | -------------------------------------------------------------------------------- |
| "p = 0.05 means there's a 5% chance H₀ is true" | ❌ Incorrect — it means there's a 5% chance of **seeing this data if H₀ is true** |
| "Low p-value = large effect size"               | ❌ Not always — it only shows statistical significance, not **magnitude**         |
| "p > 0.05 proves H₀ is true"                    | ❌ No — you just **fail to reject** H₀, not confirm it                            |

---

### 📌 Used In:

* **t-tests**
* **ANOVA**
* **Chi-square tests**
* **Regression models**
