### 🔍 What is **Feature Selection**?

**Feature selection** is the process of identifying and selecting the **most relevant features (columns)** from your dataset that contribute most to the **predictive power** of a machine learning model.

> ✅ Goal: Improve model **accuracy**, **reduce overfitting**, and **speed up** training by removing irrelevant or redundant data.

---

## 🧠 Why Is Feature Selection Important?

* Avoids **curse of dimensionality**
* Reduces **noise** and **multicollinearity**
* Improves **model performance** and **interpretability**

---

## 🔧 How to Know Which Columns to Keep?

There are **3 main approaches** to feature selection:

---

### 1️⃣ **Filter Methods**

These use **statistical techniques** to rank features independently of the model.

#### ✅ Techniques:

| Method                 | Description                                   | Use Case                                      |        |                   |
| ---------------------- | --------------------------------------------- | --------------------------------------------- | ------ | ----------------- |
| **Correlation Matrix** | Remove highly correlated features (           | r                                             | > 0.8) | For linear models |
| **Chi-Square Test**    | Tests independence between feature and target | Categorical variables                         |        |                   |
| **ANOVA F-test**       | Tests variance between groups                 | For numeric features with categorical targets |        |                   |
| **Mutual Information** | Measures info shared between feature & target | Both numerical & categorical                  |        |                   |

#### 🧪 Example (Correlation Matrix):

```python
import seaborn as sns
import matplotlib.pyplot as plt

corr = df.corr()
sns.heatmap(corr, annot=True)
```

---

### 2️⃣ **Wrapper Methods**

These use a **predictive model** to evaluate feature subsets by training and testing models repeatedly.

#### ✅ Techniques:

| Method                                  | Description                                             |
| --------------------------------------- | ------------------------------------------------------- |
| **Forward Selection**                   | Start with no features, add one at a time               |
| **Backward Elimination**                | Start with all features, remove one at a time           |
| **Recursive Feature Elimination (RFE)** | Select features recursively by ranking their importance |

#### 🧪 Example (RFE):

```python
from sklearn.feature_selection import RFE
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()
rfe = RFE(model, n_features_to_select=5)
rfe.fit(X, y)
print(rfe.support_)  # True for selected features
```

---

### 3️⃣ **Embedded Methods**

Feature selection happens **during model training**.

#### ✅ Techniques:

| Method                        | Model Used                   |
| ----------------------------- | ---------------------------- |
| **Lasso (L1 Regularization)** | Linear/logistic regression   |
| **Tree-based models**         | Random Forest, XGBoost, etc. |

#### 🧪 Example (Lasso):

```python
from sklearn.linear_model import Lasso
model = Lasso(alpha=0.01)
model.fit(X, y)
print(model.coef_)  # Zero means feature dropped
```

---

### 4️⃣ **Dimensionality Reduction: PCA**

> Principal Component Analysis (**PCA**) transforms the data into fewer dimensions while preserving variance.

* **Unsupervised technique**
* Reduces dimensionality but not ideal for interpretability

#### 🧪 Example (PCA):

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)
X_reduced = pca.fit_transform(X)
```

---

## ✅ Summary Table

| Method             | Type                     | When to Use                           |
| ------------------ | ------------------------ | ------------------------------------- |
| Correlation Matrix | Filter                   | Remove multicollinearity              |
| Chi-Square / ANOVA | Filter                   | Categorical vs Target                 |
| RFE                | Wrapper                  | Feature ranking with model            |
| Lasso              | Embedded                 | Linear model with automatic selection |
| PCA                | Dimensionality Reduction | When interpretability isn't required  |

---

## 🚀 Best Practice

* Start with **filter methods** (fast)
* Use **wrapper methods** for better accuracy (slower)
* Use **embedded methods** with regularized models
* Use **PCA** when data is high-dimensional and explainability is not key
