# 🧮 Naive Bayes

## What is Naive Bayes?

**Naive Bayes** is a family of **probabilistic supervised classification algorithms** based on **Bayes' Theorem**. It is called **"Naive"** because it makes a strong simplifying assumption: **all features are independent of each other** given the class label. Despite this assumption often being unrealistic in practice, Naive Bayes works surprisingly well and is extremely fast.

It is especially popular for **text classification** tasks such as **spam detection** and **sentiment analysis**.

---

## 📐 Mathematical Formulation (Bayes' Theorem)

```
P(A|B) = ( P(B|A) * P(A) ) / P(B)
```

For classification, the probability that a sample belongs to class `C` given features `x1, x2, ..., xn` is:

```
P(C | x1, x2, ..., xn) ∝ P(C) * P(x1|C) * P(x2|C) * ... * P(xn|C)
```

- `P(C)` = **prior** probability of class `C`
- `P(xi|C)` = **likelihood** of feature `xi` given class `C`
- The class with the **highest posterior probability** is chosen.

---

## 🧩 Variants of Naive Bayes

| Variant | When to Use |
|---|---|
| **GaussianNB** | Continuous features that follow a normal (Gaussian) distribution |
| **MultinomialNB** | Discrete counts (e.g., word counts in text) |
| **BernoulliNB** | Binary features (e.g., word present/absent, 0/1) |

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Dataset | Task |
|---|---|---|
| `spam_clasfication.ipynb` | `spam.csv` | Classify messages as spam / not spam |
| `student_performance.ipynb` | `student_performance.csv` | Predict student performance category |
| `titanic_pred_NV.ipynb` | `Titanic.csv` | Predict Titanic passenger survival |
| `Breast_Cancer_prd.ipynb` | scikit-learn built-in dataset | Classify tumors as malignant/benign |

---

## ✅ Advantages

- **Extremely fast** to train and predict — even on large datasets.
- Works well with **high-dimensional** data (e.g., text).
- Requires **very little training data**.
- Performs well on **text classification** and **multi-class** problems.
- Robust to irrelevant features.

## ❌ Disadvantages

- The **independence assumption** rarely holds in real data.
- Zero probabilities can hurt predictions unless **smoothing (Laplacian)** is applied.
- Poor at modeling **complex feature interactions**.

---

## 🎯 When to Use It

Use Naive Bayes when:
- You need a **fast, scalable** classifier.
- The task is **text classification** (spam, sentiment, topic labeling).
- Features are **relatively independent**.
- You want a strong **baseline** for classification.

---

## 📊 Common Evaluation Metrics

- **Accuracy** — overall correctness.
- **Precision & Recall** — important for spam detection (avoid false positives).
- **F1-Score** — balance between precision and recall.
- **Confusion Matrix** — error breakdown.
