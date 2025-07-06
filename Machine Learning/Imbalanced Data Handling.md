### ⚖️ What is **Imbalanced Data**?

**Imbalanced data** refers to a classification problem where the **number of instances in one class is much higher** than in the other(s).

> ✅ Example:
>
> * Fraud Detection: 99% legitimate, 1% fraud
> * Disease Diagnosis: 95% healthy, 5% sick

In such cases, traditional models may predict only the **majority class** to get high accuracy, **but fail** to detect minority class events (which are often critical).

---

## 🔍 Why Is It a Problem?

Let’s say your model predicts all patients are healthy:

* Accuracy: 95% ✅
* But it **misses all sick patients** ❌ → **Bad recall**

Hence, metrics like **Precision, Recall, F1-score**, and **ROC-AUC** become more important than **Accuracy**.

---

## 🛠️ How to Handle Imbalanced Data

---

### 1. 📉 **Undersampling** (Reduce majority class)

* Randomly remove samples from the majority class to balance the dataset.
* Risk: May lose **important information** from majority class.

```python
from imblearn.under_sampling import RandomUnderSampler

rus = RandomUnderSampler()
X_res, y_res = rus.fit_resample(X, y)
```

---

### 2. 📈 **Oversampling** (Increase minority class)

* Randomly duplicate samples from the minority class.
* Risk: May cause **overfitting** due to repeated examples.

```python
from imblearn.over_sampling import RandomOverSampler

ros = RandomOverSampler()
X_res, y_res = ros.fit_resample(X, y)
```

---

### 3. 🤖 **SMOTE (Synthetic Minority Oversampling Technique)**

* Creates **synthetic examples** (not duplicates) of the minority class by interpolating between existing ones.
* Helps avoid overfitting that random oversampling may cause.

```python
from imblearn.over_sampling import SMOTE

smote = SMOTE()
X_res, y_res = smote.fit_resample(X, y)
```

---

### 4. 🧮 **Class Weighting**

* Many ML models (like `LogisticRegression`, `RandomForest`) allow you to set **`class_weight='balanced'`**
* Automatically adjusts weights inversely proportional to class frequencies.

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression(class_weight='balanced')
```

---

### 5. 📊 **Ensemble Methods**

* Use models robust to imbalance like:

  * **BalancedRandomForestClassifier**
  * **XGBoost** with `scale_pos_weight`
  * **EasyEnsemble**, **AdaBoost**

---

## ✅ Summary Table

| Method          | Description                                  | Risk                      |
| --------------- | -------------------------------------------- | ------------------------- |
| Undersampling   | Reduce majority class                        | Loss of information       |
| Oversampling    | Duplicate minority class                     | Overfitting               |
| **SMOTE**       | Create synthetic minority samples            | Computationally intensive |
| Class Weights   | Penalize misclassification of minority class | Less control              |
| Ensemble Models | Boosting/bagging to handle imbalance         | Model complexity          |

---

## 🎯 Final Tip:

> Always evaluate performance using **Recall**, **Precision**, **F1-score**, or **ROC-AUC**, especially on the **minority class**.
