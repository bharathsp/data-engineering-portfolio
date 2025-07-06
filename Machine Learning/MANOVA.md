### 📘 What is **MANOVA**?

**MANOVA** stands for **Multivariate Analysis of Variance**.

It is an **extension of ANOVA (Analysis of Variance)** used when you have **two or more dependent variables** and want to test if **group differences exist across all those variables simultaneously**.

---

### 🧠 Simple Definition:

> While **ANOVA** compares **group means for one dependent variable**,
> **MANOVA** compares \*\*group means across **multiple dependent variables** at the same time.

---

### 🎯 Example Use Case:

Suppose you’re analyzing the effect of **teaching methods** (Traditional, Online, Hybrid) on **two outcomes**:

* Exam Score
* Project Score

With **MANOVA**, you can test:

> Do teaching methods significantly affect **both** scores **together**?

---

### 🧾 Hypotheses in MANOVA:

* **Null Hypothesis (H₀):**
  Group means are **equal** across all dependent variables.

* **Alternative Hypothesis (H₁):**
  At least **one group** differs on **at least one dependent variable**.

---

### 📐 When to Use MANOVA:

| Condition                         | Explanation                                    |
| --------------------------------- | ---------------------------------------------- |
| Multiple Dependent Variables      | 2 or more continuous variables (e.g., scores)  |
| One or More Independent Variables | Typically categorical (e.g., treatment groups) |
| You suspect correlation           | Between the dependent variables                |

---

### 📊 Assumptions:

1. **Multivariate normality**
2. **Homogeneity of covariance matrices** (equal variances & covariances across groups)
3. **Independence** of observations
4. **Linearity** between dependent variables

---

### 🐍 Python Example (Using `statsmodels`):

```python
import pandas as pd
from statsmodels.multivariate.manova import MANOVA

# Sample data
data = pd.DataFrame({
    'Group': ['A', 'A', 'B', 'B', 'C', 'C'],
    'Exam_Score': [85, 87, 78, 75, 92, 95],
    'Project_Score': [88, 90, 80, 82, 94, 96]
})

# Run MANOVA
maov = MANOVA.from_formula('Exam_Score + Project_Score ~ Group', data=data)
print(maov.mv_test())
```

---

### ✅ Benefits:

* Tests group differences on **multiple outcomes simultaneously**
* Accounts for **correlations between dependent variables**
* More **powerful** than running multiple ANOVAs

### ❌ Limitations:

* Sensitive to assumption violations
* Harder to interpret if many dependent variables
* Doesn’t say **which** variables are different — needs follow-up (e.g., post-hoc ANOVA)

---

### 🔁 When to Use ANOVA vs MANOVA:

| Situation                              | Use    |
| -------------------------------------- | ------ |
| One dependent variable                 | ANOVA  |
| Multiple dependent variables (related) | MANOVA |
