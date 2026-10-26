# DSA 2050 – Week 6 Guided Lab: Regression and Baseline Comparison

**Student Name:** Sylvain Enzo Biket Nkot
**Student ID:** 674139

---

## Lab Objective

The goal of this lab is to predict sales (`Sales_KES`) from advertising spend, store visits, discount, region, customer segment, and product category. It compares regression models against simple baselines using sound methodology: an 80/20 train/test split, leakage-safe preprocessing with scikit-learn Pipelines, 5-fold cross-validation on the training data only, residual analysis, subgroup error checks, and overfitting checks.

---

## Models Compared

| Model | Test MAE (KES) | Test RMSE (KES) | Test R² |
|---|---|---|---|
| **Ridge Regression (alpha = 1)** | **13,714** | **17,459** | **0.870** |
| Linear Regression | 13,758 | 17,470 | 0.870 |
| Decision Tree (max_depth = 4) | 23,776 | 28,768 | 0.648 |
| Median Baseline | 39,147 | 48,649 | −0.006 |
| Mean Baseline | 39,197 | 48,716 | −0.008 |

---

## Best Model

**Ridge Regression** had the lowest MAE and RMSE and the highest R² on the test set. Cross-validation confirmed it as the best, with Linear Regression practically tied.

## Selected Model MAE

**KES 13,714** on the test set (cross-validation MAE ≈ KES 15,971).
Predictions are typically off by about KES 14,000–16,000, roughly 8–9% of average sales. That is about a 65% reduction in error compared with the best baseline.

---

## Key Findings

1. **Store visits is the strongest driver of sales.** Removing `StoreVisits` dropped R² from 0.87 to 0.24, and advertising spend was the second most important predictor.
2. **An unrestricted decision tree overfits.** It reached a training MAE of 0 but a test MAE of about 26,798, worse than the shallow tree, while the linear models showed no meaningful overfitting.

---

## Limitations

1. **Small dataset:** Only 320 rows (64 in the test set), so results, especially subgroup errors, could change with a different split.
2. **Limited predictors:** Important factors such as seasonality, pricing, competitor activity, and stock availability are missing.
3. **Prediction is not causation:** The model shows associations; it does not prove that more advertising or discounts will cause higher sales.