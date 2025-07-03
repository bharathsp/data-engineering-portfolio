### 📘 What is **Logistic Regression**?

**Logistic Regression** is a **supervised machine learning algorithm** used for **binary classification** tasks — i.e., predicting one of two possible outcomes (Yes/No, 1/0, True/False).

> Even though it's called "regression", it’s actually a **classification algorithm**.

---

### 🔍 Example Use Cases:

* Will a customer **churn**? (Yes/No)
* Is an email **spam**? (Yes/No)
* Will a patient have **heart disease**? (Yes/No)

---

### ⚙️ How It Works:

It models the **probability** that a data point belongs to a certain class using the **logistic (sigmoid) function**.

#### 🔢 Mathematical Form:

For input features $X = [x_1, x_2, ..., x_n]$, logistic regression computes:

$$
z = w_0 + w_1x_1 + w_2x_2 + ... + w_nx_n
$$

$$
\text{Probability} = \sigma(z) = \frac{1}{1 + e^{-z}}
$$

* Output: a value between **0 and 1**
* You choose a threshold (usually 0.5):

  * If ≥ 0.5 → Class = 1
  * If < 0.5 → Class = 0

---

### 📉 Sigmoid Curve (S-shape):

$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$

It maps any real number to a probability between 0 and 1.

---

### 🐍 Python Example (Binary Classification):

```python
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split

# Sample data: Hours studied vs Pass (1) or Fail (0)
X = [[1], [2], [3], [4], [5], [6]]
y = [0, 0, 0, 1, 1, 1]

# Train-test split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Train logistic regression model
model = LogisticRegression()
model.fit(X_train, y_train)

# Predict
print("Predicted:", model.predict(X_test))
print("Probability:", model.predict_proba(X_test))
```

---

### ✅ Advantages:

* Simple and fast
* Provides probabilities
* Works well when the relationship between variables is **linear**

### ❌ Limitations:

* Can underperform on complex data
* Assumes a **linear decision boundary**
* Not great for multi-class (unless extended using One-vs-Rest)

---

### 📈 Extensions:

* **Multinomial Logistic Regression** – for multi-class classification
* **Regularized Logistic Regression** – uses L1/L2 penalty to avoid overfitting
