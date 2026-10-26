# DSA 2050 – Week 6 Guided Lab: Regression and Baseline Comparison

**Student Name:** Sylvain Enzo Biket_Nkot
**Student ID:** [YOUR STUDENT ID]
**Course:** DSA 2050 – Data Science Methodology
**Institution:** United States International University – Africa (USIU-Africa)

---

## Lab Objective

The goal of this lab is to predict sales (`Sales_KES`) from business characteristics: advertising spend, store visits, discount, region, customer segment, and product category. It compares regression models against simple baselines.

The lab focuses on sound methodology:
- a defensible train/test split (80/20, `random_state = 42`)
- leakage-safe preprocessing using scikit-learn Pipelines (median imputation + scaling for numeric features, most-frequent imputation + one-hot encoding for categorical features)
- 5-fold cross-validation on the training data only
- residual analysis, largest-error inspection, and subgroup error checks
- overfitting checks using shallow vs. deep decision trees

---

## Repository Structure