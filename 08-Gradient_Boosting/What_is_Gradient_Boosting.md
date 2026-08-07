# 🚀 Gradient Boosting (GBM)

## What is Gradient Boosting?

**Gradient Boosting** is an **ensemble machine learning algorithm** that builds a strong model by combining many **weak learners** (typically shallow decision trees) **sequentially**. Unlike Random Forest (bagging), where trees are built **independently in parallel**, Gradient Boosting trains each new tree to **correct the mistakes (residuals)** of the previous trees.

It works for both **regression** and **classification**, and is one of the most powerful techniques for **tabular data**.

---

## ⚙️ How It Works (Boosting by Residuals)

1. Start with a simple initial prediction (e.g., the mean of the target).
2. Compute the **residuals** — the difference between actual and predicted values:

   ```
   residual = y_actual - y_pred
   ```

3. Train a small **decision tree** to predict these residuals.
4. Update the model's predictions by adding the tree's output **scaled by a learning rate**:

   ```
   y_new = y_old + learning_rate * tree_prediction
   ```

5. Repeat steps 2–4 for many iterations. Each tree focuses on the **gradient of the loss** — hence the name "gradient" boosting.

### Key Hyperparameters

| Parameter | Role |
|---|---|
| `n_estimators` | Number of boosting stages (trees) |
| `learning_rate` | Step size per tree (lower = better generalization, needs more trees) |
| `max_depth` | Depth of each weak tree (kept small) |
| `subsample` | Fraction of data per tree (adds randomness, reduces overfitting) |

---

## 🧪 Algorithms Covered in This Folder

### Classification (`Classification/`)

| Notebook | Dataset | Task |
|---|---|---|
| `GB_Implementation.ipynb` | `Travel.csv` | Predict traveler behavior/booking |
| `About-Gradient-Boosting-classifier.ipynb` | — | Conceptual walkthrough of Gradient Boosting for classification |

### Regression (`Regression/`)

| Notebook | Dataset | Task |
|---|---|---|
| `impletation_GB_Regession.ipynb` | `cardekho_imputated.csv` | Predict used-car price |
| `2-About-gradient-boosting-regression.ipynb` | — | Conceptual walkthrough of Gradient Boosting for regression |

---

## ✅ Advantages

- **Very high predictive accuracy** — often among the best for tabular data.
- Captures **complex non-linear** relationships.
- Can handle **mixed** data types and missing values.
- Less overfitting than a single deep tree (with proper regularization).
- Highly **customizable** (loss functions, sampling, regularization).

## ❌ Disadvantages

- **Slower to train** than Random Forest (sequential training).
- **Sensitive to noisy data / outliers** — can overfit if over-trained.
- **Many hyperparameters** to tune.
- **Less interpretable** than a single decision tree.
- Requires careful **early stopping / regularization** to avoid overfitting.

---

## 🎯 When to Use It

Use Gradient Boosting when:
- You want **top-tier accuracy** on tabular data.
- You have **enough training time** (or GPU support).
- You can tune hyperparameters (`n_estimators`, `learning_rate`, `max_depth`).
- You're competing in Kaggle-style predictive tasks.

---

## 📊 Common Evaluation Metrics

- **Classification:** Accuracy, Confusion Matrix, Precision, Recall, F1-Score, ROC-AUC.
- **Regression:** MAE, MSE, RMSE, R².
- **Feature Importance** — to see which features drive the predictions.
