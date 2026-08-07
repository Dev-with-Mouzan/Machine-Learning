# 📊 Logistic Regression

## What is Logistic Regression?

Despite its name, **Logistic Regression** is a **supervised classification algorithm**, not a regression algorithm. It is used to predict the **probability** that an instance belongs to a particular class, making it ideal for **binary classification** (two classes, e.g., 0/1, Yes/No) and easily extendable to **multi-class classification**.

Instead of fitting a straight line like Linear Regression, it applies a **sigmoid (logistic) function** to squeeze the output into a probability range between **0 and 1**.

---

## 📐 Mathematical Formulation

The linear combination of inputs is passed through the **sigmoid function**:

```
z = b0 + b1*x1 + b2*x2 + ... + bn*xn

p = 1 / (1 + e^(-z))
```

- `p` = probability that the instance belongs to class 1
- `z` = linear combination of features
- If `p >= 0.5` → predicted class **1**, otherwise → predicted class **0**

The sigmoid curve guarantees the output always stays between 0 and 1.

---

## ⚙️ How It Works

1. Compute a weighted sum of the input features (`z`).
2. Pass `z` through the **sigmoid function** to get a probability.
3. Classify based on a **decision threshold** (commonly 0.5).
4. **Optimize** the weights using **Maximum Likelihood Estimation (MLE)** or **Gradient Descent**, minimizing the **Log Loss (Cross-Entropy)**:

   ```
   Loss = -[ y*log(p) + (1-y)*log(1-p) ]
   ```

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Dataset | Task |
|---|---|---|
| `titanic_prediction.ipynb` | `DataSet/Titanic.csv` | Predict Titanic passenger survival |
| `Breast_Cancer.ipynb` | scikit-learn built-in dataset | Predict whether a tumor is malignant/benign |
| `iris_prediction.ipynb` | scikit-learn built-in dataset | Multi-class classification of Iris flower species |

---

## ✅ Advantages

- Simple, fast, and highly **interpretable**.
- Outputs a **probability** for each prediction, not just a label.
- Works well with **linearly separable** data.
- Requires relatively little training data and no heavy tuning.

## ❌ Disadvantages

- Assumes a **linear decision boundary** — fails on complex, non-linear data.
- Sensitive to **outliers** and **multicollinearity**.
- Can **underfit** when the relationship is highly non-linear.

---

## 🎯 When to Use It

Use Logistic Regression when:
- The target is **categorical** (binary or multi-class).
- You need **probability estimates** alongside predictions.
- You want a **fast, interpretable baseline** model.
- The decision boundary is roughly linear.

---

## 📊 Common Evaluation Metrics

- **Accuracy** — fraction of correct predictions.
- **Precision** — of predicted positives, how many were correct.
- **Recall (Sensitivity)** — of actual positives, how many were caught.
- **F1-Score** — harmonic mean of precision and recall.
- **Confusion Matrix** — summary of TP/FP/TN/FN.
- **ROC-AUC** — trade-off between true positive and false positive rates.
