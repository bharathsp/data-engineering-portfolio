### 🌳 What is a **Decision Tree**?

A **Decision Tree** is a **supervised machine learning algorithm** used for both:

* **Classification** tasks (e.g., Yes/No, Spam/Not Spam)
* **Regression** tasks (e.g., Predicting prices or quantities)

It works by **splitting data** into smaller and smaller subsets based on **decision rules**, forming a tree-like structure.

---

### 🧠 Think of it like:

> A series of **yes/no questions** that lead you to a decision.

---

### 📊 Real-Life Example:

**"Should I play outside?"**

* Is it raining? → Yes → Don't play
* Is it hot? → No → Play

This forms a simple **tree** with decision nodes and outcomes.

---

### 🧱 Tree Components:

| Part              | Meaning                                               |
| ----------------- | ----------------------------------------------------- |
| **Root Node**     | The first decision point (top of the tree)            |
| **Decision Node** | A question that splits the data                       |
| **Leaf Node**     | Final decision or prediction                          |
| **Branches**      | The outcomes of a decision (yes/no, true/false, etc.) |

---

### ⚙️ How It Works:

1. Start at the **root node**.
2. Choose the **best feature** to split data.
3. Split the data based on that feature.
4. Repeat recursively on each split until:

   * A stopping condition is met (e.g., pure classes, max depth).
   * You reach a **leaf node**.

---

### 📏 How is the “best split” chosen?

For **classification**, using:

* **Gini Impurity**
* **Entropy / Information Gain**

For **regression**, using:

* **Mean Squared Error (MSE)**
* **Mean Absolute Error (MAE)**

---

### 🐍 Python Example (Classification):

```python
from sklearn.tree import DecisionTreeClassifier

# Sample data
X = [[1], [2], [3], [10], [11], [12]]  # Feature
y = [0, 0, 0, 1, 1, 1]                 # Class labels

# Train model
model = DecisionTreeClassifier()
model.fit(X, y)

# Predict
print("Prediction for 4:", model.predict([[4]]))  # Likely 0
```

---

### ✅ Advantages:

* Easy to understand and visualize
* Handles both numerical and categorical data
* No need for feature scaling
* Can capture **nonlinear relationships**

### ❌ Disadvantages:

* Can **overfit** (be too specific to training data)
* Not stable (small changes in data can change tree structure)
* Less accurate than ensemble methods like Random Forest

---

### 🔁 Tip: Use **Pruning** to avoid overfitting

* **Pre-pruning**: Set max depth, min samples per leaf, etc.
* **Post-pruning**: Build full tree and cut back unnecessary branches
