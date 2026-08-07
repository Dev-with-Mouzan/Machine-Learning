# 🌲 Random Forest

## What is Random Forest?

**Random Forest** is an **ensemble learning algorithm** that combines many **decision trees** to produce a more accurate and robust model. It belongs to the **bagging (Bootstrap Aggregating)** family of ensemble methods.

Instead of relying on a single tree (which is prone to overfitting), Random Forest builds **hundreds of trees**, each trained on a **random subset** of the data (with replacement) and a **random subset of features**. The final prediction is the **majority vote** (classification) or the **average** (regression) of all trees.

---

## ⚙️ How It Works (Bagging + Feature Randomness)

1. **Bootstrap sampling** — create `n` subsets of the training data by sampling **with replacement**.
2. Train a **decision tree** on each subset.
3. At each split, consider only a **random subset of features** (adds diversity).
4. Aggregate results:
   - **Classification** → majority vote across trees.
   - **Regression** → mean of all tree predictions.

This "wisdom of the crowd" dramatically reduces **variance** and **overfitting** compared to a single decision tree.

---

## 🧪 Algorithms Covered in This Folder

### Classification (`Classification/`)

| Notebook | Dataset | Task |
|---|---|---|
| `Travel_RF.ipynb` | `Travel.csv` | Predict traveler behavior/booking |
| `when_to_use_RF-Classifier.ipynb` | `Travel.csv` | Conceptual demo of when Random Forest classifiers shine |

### Regression (`Regression/`)

| Notebook | Dataset | Task |
|---|---|---|
| `Car_price_pred.ipynb` | `cardekho_imputated.csv` | Predict used-car price |
| `when_to_use_RF-Regressor.ipynb` | `cardekho_imputated.csv` | Conceptual demo of Random Forest regressors |

---

## ✅ Advantages

- **Very high accuracy** on many tasks (especially tabular data).
- **Robust to overfitting** — much better than a single tree.
- Handles **non-linear** relationships and **mixed data types**.
- Less sensitive to **outliers** and **noise**.
- Provides **feature importance** and handles missing values reasonably.
- Works with little preprocessing (no scaling required).

## ❌ Disadvantages

- **Slower to train and predict** than a single tree (many trees).
- **Less interpretable** than a single decision tree.
- Requires more memory for large forests.
- Not ideal for very **high-dimensional sparse** data (e.g., text).

---

## 🎯 When to Use It

Use Random Forest when:
- You want a **strong, robust baseline** without much tuning.
- The data is **tabular** with non-linear patterns.
- You have **moderate to large** datasets.
- You want to balance accuracy with reasonable training time.

---

## 📊 Common Evaluation Metrics

- **Classification:** Accuracy, Confusion Matrix, Precision, Recall, F1-Score, ROC-AUC.
- **Regression:** MAE, MSE, RMSE, R².
- **Feature Importance** — to understand which features drive predictions.
