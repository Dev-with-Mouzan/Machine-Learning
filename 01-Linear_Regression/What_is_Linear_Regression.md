# 📈 Linear Regression

## What is Linear Regression?

**Linear Regression** is a **supervised machine learning algorithm** used for **regression** tasks, i.e., predicting a **continuous (numeric) output** value based on one or more input features. It models the relationship between the dependent variable `y` and independent variable(s) `x` by fitting a straight line (in 2D) or a hyperplane (in higher dimensions) that best represents the data.

It is one of the simplest and most widely used algorithms in statistics and machine learning, and serves as the foundation for many advanced models.

---

## 📐 Mathematical Formulation

For a single feature (**Simple Linear Regression**):

```
y = m * x + b
```

- `y` = predicted value (target)
- `x` = input feature
- `m` = slope (weight / coefficient)
- `b` = intercept

For multiple features (**Multiple Linear Regression**):

```
y = b0 + b1*x1 + b2*x2 + ... + bn*xn
```

Where `b0` is the intercept and `b1 ... bn` are the weights/coefficients for each feature.

---

## ⚙️ How It Works

1. **Define the hypothesis** — assume the output is a linear combination of the inputs.
2. **Choose a loss function** — the model tries to minimize the error between predictions and actual values. The most common loss is the **Mean Squared Error (MSE)**:

   ```
   MSE = (1/n) * Σ (y_actual - y_pred)²
   ```

3. **Find the best-fit line** — the optimal weights are learned using one of:
   - **Ordinary Least Squares (OLS):** closed-form mathematical solution.
   - **Gradient Descent:** iteratively update weights in the direction that reduces the loss.

---

## 🧪 Algorithms Covered in This Folder

| Notebook | Dataset | Task |
|---|---|---|
| `salary_prediction.ipynb` | `Salary.csv` | Predict salary based on years of experience |
| `Housing_pred.ipynb` | `Housing.csv` | Predict house prices from features |
| `Sales_pred.ipynb` | `advertising.csv` | Predict sales from advertising spend |
| `Insurance_predicton.ipynb` | `insurance.csv` | Predict insurance charges |
| `Student_math_score_prd.ipynb` | `StudentsPerformance.csv` | Predict student math scores |

All datasets are stored in the `DataSet/` folder.

---

## ✅ Advantages

- Simple, fast, and easy to understand and interpret.
- Works well when the relationship between features and target is roughly linear.
- Coefficients give insight into the importance and effect of each feature.

## ❌ Disadvantages

- Assumes a **linear relationship** — poor performance on non-linear data.
- Sensitive to **outliers**.
- Assumes **independence** among features (little to no multicollinearity).
- Can **underfit** complex patterns.

---

## 🎯 When to Use It

Use Linear Regression when:
- The target variable is **continuous** (e.g., price, salary, score).
- There is a **linear or nearly linear** relationship between inputs and output.
- You need a **simple, interpretable** baseline model.
- You have a reasonably sized dataset without severe outliers.

---

## 📊 Common Evaluation Metrics

- **MAE (Mean Absolute Error)** — average absolute error.
- **MSE (Mean Squared Error)** — penalizes large errors more.
- **RMSE (Root Mean Squared Error)** — same units as the target, interpretable.
- **R² (R-Squared)** — proportion of variance explained by the model (0 to 1, higher is better).
