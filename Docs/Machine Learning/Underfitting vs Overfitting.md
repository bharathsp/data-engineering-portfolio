## 🔍 How to Identify Underfitting vs Overfitting

| Criteria                      | **Underfitting**                                    | **Overfitting**                                       |
| ----------------------------- | --------------------------------------------------- | ----------------------------------------------------- |
| **Training Accuracy**         | Low                                                 | High                                                  |
| **Validation Accuracy**       | Low                                                 | Much lower than training accuracy                     |
| **Gap (Train vs Validation)** | Small                                               | Large                                                 |
| **Learning Curve Behavior**   | Flat training curve                                 | Large gap between training and validation curves      |
| **Model Complexity**          | Too simple (e.g., linear model for non-linear data) | Too complex (e.g., deep tree or large neural network) |
| **Errors**                    | High bias                                           | High variance                                         |

---

### 📊 Visual Example: Learning Curves

* **Underfitting**: Both training and validation errors are high and close.
* **Overfitting**: Training error is low, but validation error is high.
* **Good fit**: Both errors are low and close together.

---

## 🧪 How to Detect It in Practice

### ✅ Step 1: Evaluate Train and Validation Accuracy

```python
from sklearn.metrics import accuracy_score

train_acc = accuracy_score(y_train, model.predict(X_train))
val_acc = accuracy_score(y_val, model.predict(X_val))

print(f"Train Accuracy: {train_acc:.2f}")
print(f"Validation Accuracy: {val_acc:.2f}")
```

### ✅ Step 2: Compare

| Scenario                                    | Diagnosis      |
| ------------------------------------------- | -------------- |
| Low train acc, low val acc                  | ❌ Underfitting |
| High train acc, low val acc                 | ❌ Overfitting  |
| High train acc, high val acc (close values) | ✅ Good fit     |

---

## 🧠 What to Do Next?

### 🔧 If Underfitting:

* Use a more complex model
* Add more features
* Reduce regularization
* Train longer

### 🔧 If Overfitting:

* Use a simpler model
* Add more training data
* Use regularization (L1, L2)
* Use dropout (for neural nets)
* Apply cross-validation

---

## ✅ Summary

| Metric              | Underfitting | Overfitting   |
| ------------------- | ------------ | ------------- |
| Train Accuracy      | Low          | High          |
| Validation Accuracy | Low          | Low           |
| Error Type          | High bias    | High variance |

> 🔍 Use **learning curves** and **train-validation scores** to visually and numerically detect underfitting or overfitting.
