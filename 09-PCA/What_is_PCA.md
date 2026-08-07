# 🧬 Principal Component Analysis (PCA)

## What is PCA?

**Principal Component Analysis (PCA)** is an **unsupervised machine learning algorithm** used for **dimensionality reduction**. It transforms a dataset with many (possibly correlated) features into a new set of **uncorrelated variables** called **principal components**, while preserving as much **variance (information)** as possible.

It is widely used for:
- **Dimensionality reduction** (reducing feature count).
- **Data visualization** (projecting high-dimensional data into 2D/3D).
- **Noise reduction** and **feature extraction**.
- Speeding up other ML models.

---

## ⚙️ How It Works

1. **Standardize** the features (mean = 0, standard deviation = 1) so no single feature dominates.
2. Compute the **covariance matrix** of the features.
3. Find the **eigenvectors** and **eigenvalues** of the covariance matrix.
   - **Eigenvectors** → directions of maximum variance (principal components).
   - **Eigenvalues** → amount of variance carried by each component.
4. Sort components by variance (largest eigenvalue first).
5. **Project** the data onto the top `k` components, dropping the rest.

The **first principal component** captures the most variance, the second captures the next most, and so on — and each is orthogonal (uncorrelated) to the previous ones.

---

## 📉 Choosing the Number of Components

Use the **explained variance ratio** (cumulative) to decide `k`:

```
Cumulative variance = Σ explained_variance_ratio_i
```

- Keep enough components to explain **~85–95%** of the variance.
- Visualize with a **scree plot** (elbow method).

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Dataset | Task |
|---|---|---|
| `implementation.ipynb` | scikit-learn dataset | Apply PCA (`n_components=2`) on standardized data to visualize and reduce dimensions |

---

## ✅ Advantages

- **Reduces dimensionality** → faster training and less memory.
- Removes **multicollinearity** and **redundant features**.
- Helps **visualize** high-dimensional data.
- Reduces **overfitting** and **noise**.
- Components are **uncorrelated** and sorted by importance.

## ❌ Disadvantages

- **Loses interpretability** — principal components are linear combinations of original features.
- Assumes **linear relationships**; fails on non-linear structures.
- Sensitive to **feature scaling** (must standardize first).
- Discarding components can **lose important information**.

---

## 🎯 When to Use It

Use PCA when:
- You have **many correlated features** and want to reduce them.
- You want to **visualize** high-dimensional data in 2D/3D.
- You need to **speed up** other algorithms.
- You're okay trading a little interpretability for performance.

---

## 📊 Common Evaluation Metrics / Outputs

- **Explained Variance Ratio** — how much variance each component captures.
- **Cumulative Explained Variance** — total information retained.
- **Scree plot / Elbow** — to choose the number of components.
