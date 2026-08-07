# 🧠 Unsupervised Machine Learning

## What is Unsupervised Learning?

**Unsupervised Machine Learning** is a type of machine learning where the algorithm learns patterns and structure from data **without labeled outputs** (no target variable). Unlike supervised learning (which maps inputs to known labels), unsupervised learning must **discover** hidden structure, groupings, or relationships on its own.

The main categories are:

- **Clustering** — group similar data points together.
- **Dimensionality Reduction** — reduce the number of features while keeping information.
- **Association Rule Learning** — discover rules/relationships between items.

---

## 🔍 Key Algorithms

### 1. K-Means Clustering

The most popular clustering algorithm. It partitions data into `k` clusters:

1. Choose `k` random **centroids**.
2. Assign each point to the **nearest centroid** (distance-based).
3. Recompute centroids as the **mean** of all points in each cluster.
4. Repeat steps 2–3 until centroids stop changing.

**Choosing `k`:** use the **Elbow Method** (plot WCSS/inertia vs. `k`) or **Silhouette Score**.

```
WCSS (Within-Cluster Sum of Squares) = Σ Σ ||x - centroid||²
```

### 2. Hierarchical Clustering

Builds a tree of clusters (**dendrogram**) either by merging similar clusters bottom-up (agglomerative) or splitting them top-down (divisive).

### 3. DBSCAN (Density-Based Spatial Clustering)

Groups points that are **densely packed** together and marks points in low-density regions as **noise/outliers**. No need to pre-specify `k`, and it can find arbitrarily shaped clusters.

### 4. PCA (Principal Component Analysis)

A **dimensionality reduction** technique that projects data onto new axes (principal components) that capture maximum variance — great for visualization and noise reduction.

### 5. Silhouette Scoring

A metric to evaluate cluster quality:

```
Silhouette Score = (b - a) / max(a, b)
```

- `a` = mean distance to other points in the same cluster.
- `b` = mean distance to points in the nearest other cluster.
- Ranges from **-1 (bad)** to **+1 (good)**; 0 means overlapping clusters.

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Content |
|---|---|
| `Intro.ipynb` | Conceptual introduction to unsupervised learning: K-Means, Hierarchical, DBSCAN, Silhouette scoring, PCA, and Kernel PCA |

---

## ✅ Advantages

- No **labeled data** required — cheaper and easier to obtain.
- Discovers **hidden patterns** humans might miss.
- Great for **exploratory data analysis**.
- Useful for **customer segmentation**, **anomaly detection**, and **feature engineering**.

## ❌ Disadvantages

- Results are **harder to evaluate** (no ground truth labels).
- Requires **domain knowledge** to interpret clusters.
- Sensitive to **feature scaling** and parameter choices (`k`, `eps`).
- Can produce **meaningless clusters** if the data has no real structure.

---

## 🎯 When to Use It

Use Unsupervised Learning when:
- You have data **without labels** and want to discover structure.
- You need **customer/entity segmentation**.
- You want to **compress or visualize** high-dimensional data.
- You need to detect **anomalies/outliers**.

---

## 📊 Common Evaluation Metrics

- **Inertia (WCSS)** — lower is better for K-Means; use for the elbow method.
- **Silhouette Score** — cluster cohesion vs. separation.
- **Dendrogram** — visualize hierarchical clustering.
- **Explained Variance** — for PCA dimensionality reduction.
