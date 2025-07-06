## 📏 1. **Z-Test**

### ✅ Used When:

* **Population standard deviation is known**
* **Sample size > 30**
* Data is **normally distributed**

### 🎯 Use Case:

> Comparing a sample mean to a known population mean.

### 🧪 Example:

"A company's historical average delivery time is 30 mins. A new method gives 100 samples with an average of 28 mins. Is it significantly faster?"

---

## 🔬 2. **T-Test**

### ✅ Used When:

* **Population standard deviation is unknown**
* **Sample size < 30**
* Data is **normally distributed**

### 🔥 Types:

| Test                  | When to Use                                            |
| --------------------- | ------------------------------------------------------ |
| **One-sample t-test** | Compare sample mean to known value                     |
| **Two-sample t-test** | Compare means of two independent groups                |
| **Paired t-test**     | Compare means of two related samples (before vs after) |

### 🧪 Example:

"Do patients on Drug A have a significantly different recovery time than those on Drug B?"

---

## 📊 3. **Chi-Square Test (χ²)**

### ✅ Used For:

* **Categorical data**
* Testing **relationships or independence** between variables

### 🔥 Types:

| Test                                | When to Use                             |
| ----------------------------------- | --------------------------------------- |
| **Chi-square Goodness-of-Fit**      | Does observed frequency match expected? |
| **Chi-square Test of Independence** | Are two categorical variables related?  |

### 🧪 Example:

"Is there a relationship between gender (male/female) and preference for a product (yes/no)?"

---

## 📈 4. **F-Test**

### ✅ Used For:

* Comparing **two or more variances**
* Underlies **ANOVA (Analysis of Variance)**

### 🧪 Example:

"Do three different fertilizers lead to different crop yields?"
Use **ANOVA (F-test)** to test if the **means differ** significantly.

---

## 🔁 5. **A/B Testing**

### ✅ Used For:

* Comparing **two versions** of a product or webpage
* Used heavily in **marketing**, **product**, **web analytics**

### 🎯 Typically involves:

* A (control group)
* B (treatment group)

➡️ Run a **t-test** or **z-test** on conversion rates to see if B is significantly better.

### 🧪 Example:

"Does version B of a landing page result in higher click-through rate than version A?"

---

## ✅ Summary Table

| Test               | Data Type                    | When to Use                         | Example                                |
| ------------------ | ---------------------------- | ----------------------------------- | -------------------------------------- |
| **Z-Test**         | Numeric (mean)               | Large sample, σ known               | Compare sample mean to population mean |
| **T-Test**         | Numeric (mean)               | Small sample, σ unknown             | Compare means of 2 groups              |
| **Chi-Square**     | Categorical                  | Test independence or distribution   | Gender vs Product Preference           |
| **F-Test / ANOVA** | Numeric (variances or means) | Compare 3+ group means or variances | Fertilizer types vs yield              |
| **A/B Testing**    | Categorical/numeric          | Compare 2 versions                  | Button A vs Button B click rate        |
