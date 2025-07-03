A **t-test** is a **statistical hypothesis test** used to determine whether there is a **significant difference between the means** of two groups (or between a group and a known value), especially when:

* Sample sizes are **small**
* Population **standard deviation is unknown**

> It’s based on the **t-distribution**, which is similar to the normal distribution but with heavier tails.

---

### 🎯 Purpose:

To answer questions like:

* "Is the average salary of Data Scientists different from \$100,000?"
* "Do Group A and Group B have significantly different test scores?"

---

### 🧪 Types of t-tests:

| Type                  | When to Use                                                        |
| --------------------- | ------------------------------------------------------------------ |
| **One-sample t-test** | Compare **sample mean** to a known or hypothesized population mean |
| **Two-sample t-test** | Compare means of **two independent groups**                        |
| **Paired t-test**     | Compare **before-and-after** means for the **same group**          |

---

### 📊 Examples:

#### 1. **One-sample t-test**

> Are students' average test scores significantly different from 70?

#### 2. **Two-sample t-test (independent)**

> Do males and females have different average heights?

#### 3. **Paired t-test**

> Did a training program improve scores (before vs. after)?

---

### 🧮 Formula (One-sample t-test):

$$
t = \frac{\bar{x} - \mu}{s / \sqrt{n}}
$$

Where:

* $\bar{x}$: sample mean
* $\mu$: population mean
* $s$: sample standard deviation
* $n$: sample size

---

### 🐍 Python Example:

#### 📌 One-Sample t-test:

```python
from scipy.stats import ttest_1samp

# Sample test scores
scores = [72, 68, 75, 70, 69]
# Test if average is different from 70
t_stat, p_val = ttest_1samp(scores, 70)

print("T-statistic:", t_stat)
print("p-value:", p_val)
```

#### 📌 Two-Sample t-test:

```python
from scipy.stats import ttest_ind

group1 = [72, 70, 68, 74]
group2 = [65, 67, 64, 66]

t_stat, p_val = ttest_ind(group1, group2)
print("T-statistic:", t_stat)
print("p-value:", p_val)
```

---

### ✅ Interpretation:

* **p-value ≤ 0.05** → Statistically significant difference → **Reject H₀**
* **p-value > 0.05** → No significant difference → **Fail to reject H₀**

---

### ⚠️ Assumptions of t-test:

* Data is **normally distributed**
* Observations are **independent**
* Equal variance (for two-sample t-test — can use Welch's t-test if not)
