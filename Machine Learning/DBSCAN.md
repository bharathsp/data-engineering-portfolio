## 🔍 What is **DBSCAN**?

**DBSCAN** stands for:

> **Density-Based Spatial Clustering of Applications with Noise**

It's an **unsupervised** clustering algorithm that forms clusters based on the **density of data points**.

---

## 📌 Key Concepts:

### 1. **ε (epsilon)**:

* Radius to search for neighboring points around a point.
* Think of it as the **neighborhood size**.

### 2. **MinPts (Minimum Points)**:

* Minimum number of points required in ε-radius to consider a point a **core point**.

---

## 🧱 Types of Points:

| Type         | Description                                                                  |
| ------------ | ---------------------------------------------------------------------------- |
| Core Point   | Has **MinPts** or more points in its ε-neighborhood.                         |
| Border Point | Has **fewer than MinPts** points in its ε-neighborhood but lies near a core. |
| Noise Point  | Not a core or border. Treated as **outlier**.                                |

---

## ⚙️ How DBSCAN Works:

1. Pick an unvisited point.
2. If it has at least **MinPts** points within distance **ε**, it becomes a **core point** → form a new cluster.
3. Expand the cluster by adding:

   * All **density-reachable** points (i.e., within ε from a core).
4. Repeat until all points are visited.

---

## 🧠 Intuition with Example:

Imagine a 2D scatter plot with dense groups of points and a few random outliers.

DBSCAN can:

* **Find arbitrary-shaped clusters**
* **Ignore the noise/outliers**

Unlike K-Means, it doesn't force you to predefine the number of clusters.

---

## 🐍 Python Example (with Scikit-learn):

```python
from sklearn.cluster import DBSCAN
import numpy as np

# Sample data
X = np.array([[1, 2], [2, 2], [2, 3],
              [8, 7], [8, 8], [25, 80]])

# DBSCAN model
db = DBSCAN(eps=2, min_samples=2)
db.fit(X)

print("Labels:", db.labels_)
```

### Output:

```python
Labels: [ 0  0  0  1  1 -1 ]
```

* Points labeled `0` and `1` belong to two different clusters.
* `-1` is a **noise point (outlier)**.

---

## ✅ Advantages:

* No need to specify the number of clusters
* Handles **arbitrary shapes**
* Identifies **outliers**
* Works well with spatial data

## ❌ Disadvantages:

* Choosing good `ε` and `MinPts` is tricky
* Doesn’t perform well when clusters have **varying densities**
* Struggles in **high-dimensional** data (curse of dimensionality)

---

## 📈 Use Cases:

* Fraud/anomaly detection
* Clustering spatial/geographical data
* Image segmentation
* Social network analysis
