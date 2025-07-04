### 🧠 What is **KNN (K-Nearest Neighbors)?**

**KNN** stands for **K-Nearest Neighbors**, a **simple, non-parametric, supervised machine learning algorithm** used for both **classification and regression**.

> 💡 KNN makes predictions based on the **similarity** (or closeness) of data points.

---

## 🔍 How Does KNN Work?

1. Choose the number of neighbors **K**.
2. Calculate the **distance** between the new input and all training data points (commonly Euclidean distance).
3. Identify the **K nearest data points**.
4. For classification: assign the **majority class** among the K neighbors.
   For regression: take the **average value** of K neighbors.

---

### 📦 Example (Classification)

Suppose you want to predict whether a fruit is an apple or orange based on weight and texture.
KNN finds the **K closest fruits** in your data and chooses the most frequent label among them.

---

## 📐 Common Distance Metric

### 🧮 Euclidean Distance:

$$
d(p, q) = \sqrt{\sum_{i=1}^{n} (p_i - q_i)^2}
$$

You can also use:

* **Manhattan distance**
* **Cosine similarity**
* **Minkowski distance**

---

## 🛠️ Python Code Example (Using scikit-learn)

```python
from sklearn.neighbors import KNeighborsClassifier

# Create model with K=3
knn = KNeighborsClassifier(n_neighbors=3)

# Train the model
knn.fit(X_train, y_train)

# Predict on test data
predictions = knn.predict(X_test)
```

---

## ⚖️ Choosing the Right **K**

* Small K (e.g., 1): model is sensitive to noise (high variance, overfitting)
* Large K: smoother decision boundary, but may **underfit**

Use **cross-validation** to find the best value of K.

---

## ✅ Advantages of KNN

* Simple and easy to implement
* No training phase (lazy learner)
* Works well with small datasets

---

## ❌ Disadvantages

* **Slow prediction** on large datasets (computes distance to all points)
* **Sensitive to irrelevant features** and feature scaling
* **Not good with high-dimensional data** (curse of dimensionality)

---

## ✅ Summary

| Feature         | KNN Algorithm                |
| --------------- | ---------------------------- |
| Type            | Supervised, Lazy Learning    |
| Use Cases       | Classification, Regression   |
| Key Concept     | Similarity/Distance-based    |
| Training Time   | None (no model learned)      |
| Prediction Time | High for large data          |
| Needs Scaling?  | ✅ Yes (e.g., StandardScaler) |
