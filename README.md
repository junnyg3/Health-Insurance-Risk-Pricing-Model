# Health Insurance Risk & Pricing Model

## Overview

This project builds an end-to-end insurance underwriting and pricing system using machine learning and simplified actuarial principles. It demonstrates how predictive modeling can be combined with pricing logic to simulate real-world insurance workflows.

---

## Objective

The goal is to:

* Predict individual medical insurance costs using machine learning
* Convert predicted costs into insurance premiums using actuarial-style pricing

The model uses the following features:

* Age
* Sex
* BMI
* Number of children
* Smoking status
* Region

Multiple regression models were evaluated, with the final model selected based on **Root Mean Squared Error (RMSE)**.

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

* Checked for missing values and data structure
* Generated summary statistics (`describe()`)
* Analyzed key relationships:

  * Smoking status vs. charges
  * Age vs. charges
  * Children vs. charges
* Identified risk patterns using grouped aggregations

---

### 2. Feature Engineering

* Applied one-hot encoding for categorical variables
* Defined feature matrix (**X**) and target (**y**)
* Performed an 80/20 train-test split
* Ensured feature alignment for predictions

---

### 3. Model Development

Trained and compared multiple models:

* Linear Regression
* Ridge Regression
* Lasso Regression
* Random Forest Regressor
* Gradient Boosting Regressor

Evaluation metrics:

* **RMSE** – measures prediction error
* **R² Score** – measures model fit

---

### 4. Model Selection

* Compared models on test data
* Ranked performance using RMSE
* Selected the best-performing model for final predictions

---

### 5. Residual Analysis

* Calculated residuals (Actual − Predicted)
* Visualized residual distribution
* Checked for randomness around zero to validate model assumptions

---

### 6. Feature Importance

* Interpreted model drivers using:

  * Coefficients (`coef_`) for linear models
  * Feature importance for tree-based models
* Key finding:

  * **Smoking status is the strongest predictor of insurance costs**

---

### 7. Actuarial Pricing Model

Predicted costs are converted into premiums using:

```
Premium = Predicted Cost × (1 + Risk Margin + Admin Load)
```

Assumptions:

* Risk Margin = 15%
* Administrative Load = 10%

---

### 8. Monthly Payment Calculation

```
Monthly Payment = Premium / 12
```

Optional adjustments can simulate financing effects.

---

### 9. Risk Classification

Policyholders are grouped into risk tiers:

* **Low Risk**: < $5,000
* **Medium Risk**: $5,000 – $15,000
* **High Risk**: > $15,000

---

## Key Insights

* Smoking status has the largest impact on insurance costs
* Tree-based models tend to capture nonlinear relationships better
* Combining ML predictions with pricing logic creates a realistic underwriting simulation

---

## Project Structure

```
Health-Insurance-Risk-Pricing-Model/
│
├── insurance_pricing_model.ipynb
├── insurance.csv
├── README.md
```

---

## How to Run

1. Clone the repository:

```
git clone https://github.com/yourusername/Health-Insurance-Risk-Pricing-Model.git
```

2. Install dependencies:

```
pip install pandas numpy scikit-learn matplotlib
```

3. Run the Jupyter Notebook:

```
jupyter notebook
```

---

## Why This Project Matters

This project mirrors key components of real actuarial and underwriting workflows:

* Risk assessment using data
* Predictive modeling
* Pricing and premium calculation
* Customer segmentation

It is designed to showcase skills relevant to:

* Actuarial Analyst roles
* Data Analyst roles
* Entry-level Data Science positions

---

## Future Improvements

* Add more advanced models (e.g., XGBoost)
* Incorporate cross-validation
* Build a simple web app for user input
* Add real-world constraints (regulation, profit targets)

---

## Author

Jonathan Garcia


Consider giving the repo a star!
