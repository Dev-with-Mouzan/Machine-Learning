# 🔍 K-Nearest Neighbors (KNN)

## What is KNN?

**K-Nearest Neighbors (KNN)** is a **supervised machine learning algorithm** used for both **classification** and **regression**. It is one of the simplest ML algorithms because it makes **no assumptions** about the underlying data distribution (a **lazy / instance-based learner** — it does not "train" a model, it stores the data and makes decisions at prediction time).

The idea is simple: **an object is classified based on the majority class (or average value) of its `k` nearest neighbors** in the feature space.

---

## 📐 How It Works

1. **Store** all training examples.
2. For a new query point, compute its **distance** to every training example.
3. Select the **`k` nearest neighbors** (smallest distances).
4. **Classification:** assign the most frequent class among those `k` neighbors (majority vote).
5. **Regression:** assign the **average (mean)** of the target values of the `k` neighbors.

### Distance Metrics

The most common distance measures are:

```
Euclidean:    d = sqrt( Σ (x_i - y_i)² )
Manhattan:    d = Σ |x_i - y_i|
Minkowski:    d = ( Σ |x_i - y_i|^p )^(1/p)
```

---

## 🔢 Choosing the Right `k`

- **Small `k`** → sensitive to noise, prone to **overfitting**.
- **Large `k`** → smoother decision boundary, but may **underfit**.
- The optimal `k` is usually found via **cross-validation** or the **elbow method**.

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Dataset | Task |
|---|---|---|
| `flower_spec_prd.ipynb` | `Iris.csv` | Classify Iris flower species |
| `Wine_Quality_prd.ipynb` | `WineQT.csv` | Predict wine quality category |
| `Breast_Cancer_prd.ipynb` | scikit-learn built-in dataset | Classify tumors as malignant/benign |

---

## ✅ Advantages

- Extremely **simple to understand and implement**.
- No training phase → fast training (but slow prediction).
- Works well for **small to medium** datasets.
- Naturally supports **multi-class** problems.

## ❌ Disadvantages

- **Slow prediction** on large datasets (must compute distance to all points).
- Highly sensitive to **irrelevant features** and **feature scale** → requires **normalization/standardization**.
- Performance degrades in **high-dimensional** spaces ("curse of dimensionality").
- Sensitive to **noise** and **imbalanced data**.

---

## 🎯 When to Use It

Use KNN when:
- The dataset is **small to medium** sized.
- You need a **simple, non-parametric** baseline.
- Decision boundaries are **non-linear**.
- You can properly **scale features** and choose a good `k`.

---

## 📊 Common Evaluation Metrics

- **Accuracy** — correct predictions / total predictions.
- **Confusion Matrix** — TP/FP/TN/FN breakdown.
- **Precision, Recall, F1-Score** — for imbalanced classification.
- **Cross-Validation accuracy** — to pick the best `k`.
