### 📊 What is **ANOVA**?

**ANOVA** stands for **Analysis of Variance**.

It is a **statistical test** used to determine whether there are **significant differences between the means of three or more independent groups**.

---

### 🎯 Use Case:

> “Do students from three different schools have the same average test scores?”

* If **Yes** → No significant difference (means are equal)
* If **No** → At least one group mean is different

---

### 🧠 Why Not Just Use Multiple t-tests?

Because:

* It **increases the risk of Type I error** (false positives)
* ANOVA controls this by comparing **all group means simultaneously**

---

### 📚 Types of ANOVA:

| Type                        | Use Case Example                                             |
| --------------------------- | ------------------------------------------------------------ |
| **One-Way ANOVA**           | One factor, 3+ groups → e.g., Exam scores by school          |
| **Two-Way ANOVA**           | Two factors → e.g., Exam scores by school and gender         |
| **Repeated Measures ANOVA** | Same group measured multiple times → e.g., before/after test |

---

### 🧮 One-Way ANOVA – How It Works:

1. Calculate **Between-group variability** (difference between group means)
2. Calculate **Within-group variability** (variation inside each group)
3. Compute **F-statistic**:

$$
F = \frac{\text{Variance between groups}}{\text{Variance within groups}}
$$

4. Use F and degrees of freedom to get a **p-value**

---

### 🐍 Python Example (One-Way ANOVA):

```python
from scipy.stats import f_oneway

# Sample test scores from 3 groups
group1 = [85, 90, 88]
group2 = [70, 65, 72]
group3 = [78, 80, 75]

f_stat, p_val = f_oneway(group1, group2, group3)

print("F-statistic:", f_stat)
print("p-value:", p_val)
```

---

### ✅ Interpretation:

* **p-value ≤ 0.05** → At least one group mean is significantly different → **Reject H₀**
* **p-value > 0.05** → No significant difference → **Fail to reject H₀**

---

### 🧾 Assumptions of ANOVA:

* Groups are **independent**
* Residuals are **normally distributed**
* Groups have **equal variances** (homoscedasticity)

---

### 📈 Real-World Applications:

* A/B/n testing (e.g., comparing multiple ad versions)
* Comparing exam results across departments
* Clinical trials comparing multiple drug groups
