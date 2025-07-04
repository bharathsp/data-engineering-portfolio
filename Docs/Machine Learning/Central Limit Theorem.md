### 📚 What is the **Central Limit Theorem (CLT)?**

The **Central Limit Theorem** is a fundamental concept in statistics that states:

> **"Regardless of the population's distribution, the sampling distribution of the sample mean will approach a normal distribution as the sample size becomes large."**

---

### 🧠 In Simple Terms:

Even if your data is **not normally distributed**, the **mean of samples** taken from it will be **approximately normally distributed** if:

* The **sample size is large** (usually **n ≥ 30**)
* The samples are **independent** and **identically distributed (i.i.d.)**

---

### 🧪 Key Components

| Term                               | Meaning                                                       |
| ---------------------------------- | ------------------------------------------------------------- |
| **Population**                     | The entire dataset or group you're studying                   |
| **Sample**                         | A subset of data taken from the population                    |
| **Sampling Distribution**          | Distribution of a statistic (like mean) over many samples     |
| **Mean of Sample Means**           | Will be close to the **population mean (μ)**                  |
| **Shape of Sampling Distribution** | Approaches a **normal distribution** as sample size increases |

---

### 🔍 Why Is It Important?

The CLT allows us to:

* Use **normal distribution** tools even when the data isn't normal
* Build **confidence intervals**
* Conduct **hypothesis tests** using z-tests and t-tests

---

### 📈 Visual Example

* Population: Skewed or uniform
* Take many random samples (size ≥ 30)
* Plot the **means of those samples**
* Result: You get a **bell-shaped curve (normal distribution)**

---

### 📐 Example:

Imagine rolling a **die** (which is **not normally distributed**).

* Roll it **100 times**, record the **average**
* Repeat that **1,000 times**
* Plot the **1,000 averages** → You'll get a **normal distribution**

---

### 🧪 Python Code Example

```python
import numpy as np
import matplotlib.pyplot as plt

# Simulate population: rolling a 6-sided die
population = np.random.randint(1, 7, size=100000)

sample_means = []
for _ in range(1000):
    sample = np.random.choice(population, size=30)
    sample_means.append(np.mean(sample))

plt.hist(sample_means, bins=30, density=True, color='skyblue', edgecolor='black')
plt.title("Sampling Distribution of Sample Means (CLT)")
plt.xlabel("Sample Mean")
plt.ylabel("Frequency")
plt.show()
```

---

## ✅ Summary

| Feature         | Description                                                               |
| --------------- | ------------------------------------------------------------------------- |
| **CLT**         | Sampling distribution of the mean becomes normal as sample size increases |
| **Sample Size** | Typically ≥ 30                                                            |
| **Use Cases**   | Hypothesis testing, confidence intervals                                  |
| **Power**       | Works even with non-normal populations                                    |
