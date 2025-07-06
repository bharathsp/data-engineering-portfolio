### 🧪 What is **Hypothesis Testing**?

**Hypothesis Testing** is a **statistical method** used to make decisions or inferences about a population based on **sample data**.

> It helps you answer questions like:
> “Is this effect real, or could it have happened by chance?”

---

### 🔍 Real-World Example:

Suppose a new drug claims to lower blood pressure better than the old one.
How do you **verify** that this claim is statistically true?
→ You use **hypothesis testing**.

---

### 📚 Key Concepts:

| Term                            | Meaning                                                                   |
| ------------------------------- | ------------------------------------------------------------------------- |
| **Null Hypothesis (H₀)**        | The assumption that there is **no effect** or **no difference**.          |
| **Alternative Hypothesis (H₁)** | The assumption that there **is an effect** or **a difference**.           |
| **p-value**                     | Probability of observing results as extreme as the sample, if H₀ is true. |
| **α (alpha)**                   | Significance level (commonly 0.05). Threshold to reject H₀.               |
| **Test Statistic**              | A value calculated from sample data to help decide whether to reject H₀.  |

---

### 🧪 Steps in Hypothesis Testing:

1. **Formulate Hypotheses**

   * H₀: μ = μ₀ (e.g., average weight = 70 kg)
   * H₁: μ ≠ μ₀ (two-tailed), μ > μ₀, or μ < μ₀ (one-tailed)

2. **Choose Significance Level (α)**

   * Usually 0.05 (5%)

3. **Select the Right Test**

   * Depends on data type, sample size, and distribution
   * Examples: t-test, z-test, chi-square test, ANOVA

4. **Compute Test Statistic and p-value**

5. **Make Decision**

   * If **p-value ≤ α** → Reject H₀ (evidence supports H₁)
   * If **p-value > α** → Fail to reject H₀ (not enough evidence)

---

### 🧠 Common Types of Tests:

| Test                | When to Use                                             |
| ------------------- | ------------------------------------------------------- |
| **Z-test**          | Large sample, known population std dev                  |
| **T-test**          | Small sample, unknown std dev                           |
| **Chi-square test** | Categorical data, goodness-of-fit or independence tests |
| **ANOVA**           | Compare means across **3+ groups**                      |
| **Proportion test** | Comparing proportions (e.g., A/B testing)               |

---

### 🐍 Python Example (One-Sample T-test):

```python
from scipy import stats

# Sample data
sample = [72, 74, 69, 71, 68, 70, 73]
# Test if mean = 70
t_stat, p_value = stats.ttest_1samp(sample, 70)

print("T-statistic:", t_stat)
print("p-value:", p_value)
```

---

### ✅ Interpretation:

* **Low p-value (≤ 0.05)** → Strong evidence **against** H₀ → **Reject** H₀
* **High p-value (> 0.05)** → Weak evidence against H₀ → **Fail to reject** H₀

---

### ❗ Caution:

* **Failing to reject H₀ ≠ H₀ is true**
* A low p-value shows **statistical significance**, not practical importance
* Multiple testing increases risk of **false positives** (adjust with Bonferroni, FDR)
