# 🌳 Decision Tree

## What is a Decision Tree?

A **Decision Tree** is a **supervised machine learning algorithm** used for both **classification** and **regression**. It makes predictions by learning a series of **if-then-else rules** from the data and representing them as a **tree structure**:

- **Root Node** — the topmost node; the first split on the most important feature.
- **Internal Nodes** — each represents a decision/test on a feature.
- **Branches** — the outcome of a test (edge to the next node).
- **Leaf Nodes** — final output (a class label or a continuous value).

It works by repeatedly splitting the data into subsets that are as **pure** (homogeneous) as possible.

---

## ⚙️ How It Works (Splitting Criteria)

At each node, the algorithm chooses the feature that best separates the data using one of these impurity measures:

| Criterion | Purpose | Formula Idea |
|---|---|---|
| **Gini Impurity** | Classification | Measures how often a random sample would be mislabeled |
| **Entropy / Information Gain** | Classification | Measures reduction in uncertainty after a split |
| **MSE / Variance** | Regression | Minimizes variance within child nodes |

```
Gini = 1 - Σ p_i²
Entropy = - Σ p_i * log2(p_i)
```

The tree keeps splitting until a stopping condition is met (max depth, min samples per leaf, no impurity gain, etc.).

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Dataset | Task |
|---|---|---|
| `Titanic_Desion_tree.ipynb` | `Titanic.csv` | Predict Titanic passenger survival |
| `Student_performance.ipynb` | `student_performance.csv` | Predict student performance category |

---

## ✅ Advantages

- **Easy to understand and interpret** — can be visualized as a flowchart.
- Handles **both numeric and categorical** features.
- Requires **little data preprocessing** (no scaling needed).
- Captures **non-linear relationships** automatically.
- Provides **feature importance** for free.

## ❌ Disadvantages

- **Prone to overfitting** — a deep tree memorizes the training data.
- **Unstable** — small changes in data can produce a very different tree.
- Sensitive to **imbalanced data**.
- Can be biased toward features with **more levels/categories**.

---

## 🎯 When to Use It

Use a Decision Tree when:
- You need a **human-readable / explainable** model.
- You want a fast, non-parametric baseline with little preprocessing.
- You need **feature importance** insights.
- The dataset is small to moderate (large data → use Random Forest/Boosting).

---

## 📊 Common Evaluation Metrics

- **Accuracy / Confusion Matrix** — classification.
- **Precision, Recall, F1-Score** — for imbalanced data.
- **Gini / Entropy decrease** — to interpret splits.
- **Pruning** (pre/post) — to control overfitting.
