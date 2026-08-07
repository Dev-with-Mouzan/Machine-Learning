# 🧱 Support Vector Machines (SVM)

## What is SVM?

**Support Vector Machine (SVM)** is a powerful **supervised machine learning algorithm** used mainly for **classification** (and also **regression** — SVR). It finds the **optimal hyperplane** that best separates different classes with the **maximum margin**.

The "support vectors" are the data points **closest to the hyperplane** that define the decision boundary. SVM maximizes the distance (margin) between these points and the hyperplane, which leads to better generalization on unseen data.

---

## 📐 Key Concept: Maximum Margin Hyperplane

For a linearly separable problem, SVM finds the line/hyperplane such that the distance to the nearest point from each class is **maximized**.

```
y = sign( w·x + b )
```

- `w` = weight vector (orientation of hyperplane)
- `b` = bias term (offset)
- The margin is `2 / ||w||` — SVM maximizes the margin.

---

## 🌐 Handling Non-Linear Data (The Kernel Trick)

When data is **not linearly separable**, SVM uses **kernels** to project the data into a **higher-dimensional space** where it *becomes* linearly separable — without explicitly computing the transformation (the "kernel trick").

### Common Kernels

| Kernel | Description |
|---|---|
| **Linear** | Best for linearly separable data |
| **Polynomial** | Adds polynomial combinations of features |
| **RBF (Radial Basis Function)** | Default & most popular — handles non-linear data well |
| **Sigmoid** | Similar to a neural network activation |

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Dataset | Task |
|---|---|---|
| `Spam_Classification_svm.ipynb` | `spam.csv` | Classify messages as spam / not spam |
| `Titanic_prediction_Svm.ipynb` | `Titanic.csv` | Predict Titanic passenger survival |
| `student_performance_Svm.ipynb` | `student_performance.csv` | Predict student performance category |

---

## ✅ Advantages

- **Very effective in high-dimensional spaces**.
- Works well when the number of features exceeds the number of samples.
- Great generalization thanks to the **max-margin** principle.
- The **kernel trick** makes it powerful for non-linear problems.
- Memory efficient — only the **support vectors** matter.

## ❌ Disadvantages

- **Slow** to train on **large datasets**.
- Sensitive to **feature scaling** (must standardize).
- Difficult to **interpret** (especially with non-linear kernels).
- Performance is sensitive to the choice of **kernel and hyperparameters** (`C`, `gamma`).
- Less suitable for **noisy or overlapping** classes.

---

## 🎯 When to Use It

Use SVM when:
- You have **high-dimensional** data (e.g., text, images).
- The dataset is **small to medium** sized.
- You need a **robust, well-generalizing** classifier.
- You can tune the kernel and regularization parameters (`C`, `gamma`).

---

## 📊 Common Evaluation Metrics

- **Accuracy** — overall correctness.
- **Confusion Matrix** — TP/FP/TN/FN.
- **Precision, Recall, F1-Score** — especially for imbalanced data.
- **ROC-AUC** — class separation quality.
