### 🔍 **What is Hierarchical Clustering?**

Hierarchical clustering is an **unsupervised machine learning algorithm** used to build a **hierarchy of clusters**.

It produces a **tree-like structure (dendrogram)** that shows how data points are merged (or split) step by step.

There are two main types:

1. **Agglomerative (bottom-up)** – starts with individual points and merges them into clusters.
2. **Divisive (top-down)** – starts with one big cluster and splits it into smaller clusters.

⚠️ Most commonly used: **Agglomerative Hierarchical Clustering**

---

### ⚙️ **How Agglomerative Clustering Works:**

Given a dataset with `n` points:

1. **Start**: Treat each point as its own cluster (n clusters).
2. **Compute distances** between every pair of clusters.
3. **Merge the closest pair** of clusters.
4. **Recompute distances** between the new cluster and remaining ones.
5. **Repeat** steps 3–4 until all points are merged into a single cluster.

---

### 📏 **Distance Measures** (called *linkage criteria*):

* **Single Linkage**: Min distance between any two points across clusters
* **Complete Linkage**: Max distance between any two points across clusters
* **Average Linkage**: Average distance between all pairs of points
* **Ward’s Method**: Minimizes the total variance (most popular for numeric data)

---

### 🌳 **What is a Dendrogram?**

A **dendrogram** is a tree diagram that shows how clusters are merged or split.

You can **cut the dendrogram** at a particular height to choose how many clusters to keep.

---

### 🧠 **Use Case Example:**

Let’s say we have 5 data points:

A(1), B(2), C(3), D(10), E(11)

At each step:

* Merge A and B → (A,B)
* Then merge (A,B) with C → (A,B,C)
* Then merge D and E → (D,E)
* Finally merge (A,B,C) and (D,E)

Dendrogram helps visualize **at what distance** these merges happen.

---

### 🐍 Python Example (using SciPy):

```python
from scipy.cluster.hierarchy import dendrogram, linkage
import matplotlib.pyplot as plt

# Sample data
import numpy as np
X = np.array([[1], [2], [3], [10], [11]])

# Perform hierarchical clustering
linked = linkage(X, method='ward')

# Plot dendrogram
dendrogram(linked,
           labels=['A', 'B', 'C', 'D', 'E'],
           distance_sort='ascending')
plt.title('Hierarchical Clustering Dendrogram')
plt.xlabel('Data Points')
plt.ylabel('Distance')
plt.show()
```

---

### ✅ Pros:

* Doesn’t require specifying number of clusters up front
* Can be visualized as a dendrogram
* Good for small datasets

### ❌ Cons:

* Computationally expensive (O(n²) or worse)
* Sensitive to noise and outliers
* Once merged/split, can’t undo decisions
