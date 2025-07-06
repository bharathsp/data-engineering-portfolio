### 📊 What is **Normal Distribution**?

The **Normal Distribution**, also called the **Gaussian Distribution**, is a **probability distribution** that is **symmetric and bell-shaped**, representing how values of a variable are distributed around the **mean**.

---

### 📐 Characteristics of Normal Distribution:

| Feature                  | Description                                            |
| ------------------------ | ------------------------------------------------------ |
| **Shape**                | Bell curve                                             |
| **Mean = Median = Mode** | All are equal                                          |
| **Symmetry**             | Perfectly symmetric about the mean                     |
| **Spread**               | Defined by **mean (μ)** and **standard deviation (σ)** |
| **Total Area**           | Under the curve = 1 (100%)                             |

---

### 🧠 Mathematical Formula:

$$
f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{ -\frac{1}{2} \left( \frac{x - \mu}{\sigma} \right)^2 }
$$

Where:

* $\mu$ = mean
* $\sigma$ = standard deviation
* $x$ = variable

---

### 📊 Empirical Rule (68–95–99.7 Rule):

* 68% of data falls within **1σ** of the mean
* 95% within **2σ**
* 99.7% within **3σ**

---

### 📈 Real-Life Examples:

| Scenario               | Description                                                            |
| ---------------------- | ---------------------------------------------------------------------- |
| **Human Heights**      | Most people are around average height; few are very short or very tall |
| **Exam Scores**        | Most students score near the average; few fail or top                  |
| **Measurement Errors** | Instrumental readings often follow a normal distribution               |

---

### 🧪 Python Example

```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

data = np.random.normal(loc=0, scale=1, size=1000)
sns.histplot(data, kde=True)
plt.title("Normal Distribution")
plt.show()
```

---

## ✅ Summary

| Term                       | Description                                          |
| -------------------------- | ---------------------------------------------------- |
| **Normal Distribution**    | Bell-shaped curve representing data distribution     |
| **Mean (μ)**               | Center of the distribution                           |
| **Standard Deviation (σ)** | Spread of the data                                   |
| **Symmetry**               | Equal on both sides of the mean                      |
| **Applications**           | In statistics, ML, error analysis, natural processes |
