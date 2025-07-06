**K-Means Clustering** is an **unsupervised machine learning algorithm** used to group data into **K distinct non-overlapping clusters** based on feature similarity.

---

### 🔑 **Key Concepts:**

* **Unsupervised**: No labeled data is provided.
* **Clusters**: Groups of similar data points.
* **Centroid**: The center of a cluster.
* **K**: The number of clusters you want the algorithm to find.

---

### ⚙️ **How It Works:**

1. **Choose K** – the number of clusters.
2. **Initialize** – randomly place K centroids.
3. **Assign** – assign each data point to the nearest centroid (using distance metric like Euclidean distance).
4. **Update** – recalculate the centroids as the mean of all points in the cluster.
5. **Repeat** – steps 3 and 4 until centroids don't change much (convergence).

---

### 📊 **Simple Example in 2D:**

Suppose you have points scattered in space. You want to group them into 3 clusters (K=3):

* K-Means will find 3 centroids.
* Points will be grouped based on their proximity to these centroids.

---

### 🧠 **Real-Life Applications:**

* Customer segmentation
* Image compression
* Document clustering
* Anomaly detection

---

### 🐍 **Python Example:**

```python
from sklearn.cluster import KMeans
import numpy as np

# Sample data
X = np.array([[1, 2], [1, 4], [1, 0],
              [10, 2], [10, 4], [10, 0]])

# Apply KMeans
kmeans = KMeans(n_clusters=2, random_state=0)
kmeans.fit(X)

print("Cluster Centers:", kmeans.cluster_centers_)
print("Labels:", kmeans.labels_)
```

---

### ⚠️ **Important Notes:**

* You must choose **K** manually (though methods like Elbow Method help).
* It assumes **spherical clusters** (i.e., similar size).
* Sensitive to **initial centroid placement** and **outliers**.

Great! Let’s walk through **K-Means clustering step-by-step** with a **simple set of random 2D points**, and show how **iterations** work to form clusters.

---

### 🎯 Objective:

Cluster the following **6 random 2D points** into **K = 2 clusters**.

---

### 📍 Step 0: Sample Data Points

We'll use these coordinates:

| Point | Coordinates |
| ----- | ----------- |
| A     | (1, 2)      |
| B     | (1, 4)      |
| C     | (1, 0)      |
| D     | (10, 2)     |
| E     | (10, 4)     |
| F     | (10, 0)     |

Let’s denote them as a NumPy array:

```python
X = np.array([[1,2], [1,4], [1,0], [10,2], [10,4], [10,0]])
```

---

### 🔁 Step 1: Initialization

Randomly pick **2 centroids**. Let’s pick:

* Centroid 1 (C1) = (1, 2) ✅
* Centroid 2 (C2) = (10, 2) ✅

---

### 🧮 Step 2: Assign Each Point to Closest Centroid

Use **Euclidean Distance**:

| Point | Distance to C1 | Distance to C2 | Assigned To |
| ----- | -------------- | -------------- | ----------- |
| A     | 0              | 9              | C1          |
| B     | 2              | 9.22           | C1          |
| C     | 2              | 9.22           | C1          |
| D     | 9              | 0              | C2          |
| E     | 9.22           | 2              | C2          |
| F     | 9.22           | 2              | C2          |

✅ **Cluster 1**: A, B, C
✅ **Cluster 2**: D, E, F

---

### 🧮 Step 3: Update Centroids

Take **mean** of points in each cluster:

* New C1 = Mean of (1,2), (1,4), (1,0) = (1, (2+4+0)/3) = (1, 2)
* New C2 = Mean of (10,2), (10,4), (10,0) = (10, (2+4+0)/3) = (10, 2)

😲 **Centroids didn't change**, so we're done.

---

### ✅ Final Clusters:

* Cluster 1: A, B, C → Close to (1, 2)
* Cluster 2: D, E, F → Close to (10, 2)

---

### 📈 Visual Interpretation:

If plotted, you’d see two vertical stacks of 3 points on x = 1 and x = 10 — KMeans easily separates them.

---

### 🔄 If the initial centroids were different?

Let’s say random centroids were:

* C1 = (1, 0)
* C2 = (1, 4)

The first assignment would be different, and centroids would shift in iterations before stabilizing.

---

### Summary of Iterations:

1. Randomly choose K centroids.
2. Assign each point to the nearest centroid.
3. Recalculate centroids.
4. Repeat steps 2–3 until centroids stop changing.
