# Health-Insurance-Risk-Pricing-Model
## Project Summary: Insurance Cost Prediction & Pricing Model

This project builds an end-to-end insurance underwriting and pricing system using machine learning and simplified actuarial concepts.


## Objective

The goal of this project is to predict individual medical insurance costs and convert those predictions into insurance premiums using pricing logic that reflects real-world insurance workflows.

A machine learning model is trained using features such as:
- Age  
- Sex  
- BMI  
- Number of children  
- Smoking status  
- Region  

Multiple regression models were evaluated, and the best-performing model was selected based on RMSE.


## Key Components

### 1. Data Exploration (EDA)
- Checked for missing values and dataset structure
- Generated summary statistics using `describe()`
- Analyzed relationships between key variables and insurance charges:
  - Smoking status vs charges
  - Age vs charges
  - Number of children vs charges
- Performed grouped aggregations to identify risk patterns


### 2. Feature Engineering
- Applied one-hot encoding to convert categorical variables into numerical format
- Defined feature matrix (X) and target variable (y)
- Split data into training and testing sets (80/20 split)
- Ensured feature alignment between training and prediction data


### 3. Model Development
- Trained multiple regression models:
  - Linear Regression  
  - Ridge Regression  
  - Lasso Regression  
  - Random Forest Regressor  
  - Gradient Boosting Regressor  
- Evaluated models using:
  - **RMSE** (prediction error)
  - **R² score** (goodness of fit)
- Selected the best model based on lowest RMSE


### 4. Model Evaluation & Selection
- Compared model performance on test data
- Ranked models by RMSE
- Selected the best-performing model for final predictions
- Generated final predictions using the selected model


### 5. Residual Analysis
- Calculated residuals (actual vs predicted values)
- Visualized residual behavior to assess model performance
- Checked for randomness around zero to validate model fit


### 6. Feature Importance / Interpretation
- Extracted feature importance using:
  - Coefficients (`coef_`) for linear models
  - Feature importance scores (`feature_importances_`) for tree-based models
- Identified most influential variables affecting insurance cost
- Smoking status emerged as the strongest predictor of charges


### 7. Actuarial Pricing Model
- Converted predicted medical costs into insurance premiums:

$
\text{Premium} = \text{Predicted Cost} \times (1 + \text{Risk Margin} + \text{Admin Load})
$

- Assumed:
  - Risk Margin = 15%
  - Administrative Load = 10%


### 8. Monthly Payment System
- Converted annual premiums into monthly payments:

$
\text{Monthly Payment} = \frac{\text{Premium}}{12}
$

- Optional adjustment can be applied to simulate financing effects

### 9. Risk Classification
Individuals were grouped into risk tiers based on predicted cost:
- **Low Risk**: < 5,000  
- **Medium Risk**: 5,000 – 15,000  
- **High Risk**: > 15,000  


## Final Insight

This project simulates a real-world actuarial workflow by combining:

- Machine learning-based prediction  
- Model evaluation and selection  
- Residual and feature importance analysis  
- Insurance pricing logic  
- Risk classification and payment structuring  

It demonstrates how data science can be applied to build simplified underwriting and pricing systems similar to those used in the insurance industry.
