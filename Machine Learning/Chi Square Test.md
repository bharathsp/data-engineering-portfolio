### 🔍 What is the **Chi-Square (χ²) Test**?

The **Chi-Square test** is a **statistical test** used to determine if there is a **significant association between two categorical variables** or if an **observed distribution differs** from an expected one.

It’s commonly used for:

* Testing **independence** between variables in a contingency table
* Testing **goodness-of-fit** for a theoretical distribution

---

### 📚 Two Main Types of Chi-Square Tests:

| Test Type                           | Use Case Example                                       |
| ----------------------------------- | ------------------------------------------------------ |
| **Chi-Square Test of Independence** | Is gender associated with purchase behavior?           |
| **Chi-Square Goodness-of-Fit Test** | Does the observed dice roll match a fair distribution? |

---

### 🧠 1. **Chi-Square Test of Independence**

Used to test if **two categorical variables are related**.

> Example: Is there a relationship between **education level** and **voting preference**?

✅ Uses a **contingency table** (cross-tabulation of variables)
✅ Compares **observed** vs **expected** frequencies

---

### 🧠 2. **Chi-Square Goodness-of-Fit Test**

Used to check if an **observed frequency distribution** matches an **expected distribution**.

> Example: Do colors in an M\&M pack occur equally?

---

### 🧮 Chi-Square Formula:

$$
\chi^2 = \sum \frac{(O - E)^2}{E}
$$

Where:

* $O$ = observed frequency
* $E$ = expected frequency

---

### 🐍 Python Example:

#### 📌 Chi-Square Test of Independence:

```python
import scipy.stats as stats
import pandas as pd

# Contingency Table
data = [[30, 10],  # Group A: Yes, No
        [20, 40]]  # Group B: Yes, No

# Perform Chi-Square Test
chi2, p, dof, expected = stats.chi2_contingency(data)

print("Chi-Square Statistic:", chi2)
print("p-value:", p)
print("Degrees of Freedom:", dof)
print("Expected Frequencies:\n", expected)
```

---

### ✅ Interpretation:

* **p-value ≤ 0.05** → Variables are likely **dependent** → **Reject H₀**
* **p-value > 0.05** → Variables are likely **independent** → **Fail to reject H₀**

---

### ⚠️ Assumptions:

* Data is **categorical**
* Expected frequency in each cell ≥ 5 (for reliability)
* Observations are **independent**

---

### 🔁 Real-World Applications:

* Market research (e.g., preference vs age group)
* A/B testing (click behavior vs version)
* Genetics (Mendelian ratios)
* Survey analysis
