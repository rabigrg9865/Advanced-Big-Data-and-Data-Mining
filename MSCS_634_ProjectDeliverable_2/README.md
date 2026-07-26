# MSCS 634 Project Deliverable 2: Regression Modeling and Performance Evaluation

## Dataset and Goal
This deliverable uses the cleaned UCI Red Wine Quality dataset from Deliverable 1 to predict wine quality with regression models.

## Modeling Process
- Added engineered predictors: sulfur ratio, acid balance, and alcohol-sulphates interaction.
- Built Multiple Linear Regression and Ridge Regression models.
- Evaluated models using R-squared, MSE, RMSE, and 5-fold cross-validation.
- Created visualizations comparing RMSE and actual versus predicted quality.

## Key Observations
Regression performance is modest, showing that chemical attributes explain part, but not all, of perceived wine quality. Ridge Regression is the preferred model when it offers similar or lower RMSE because regularization improves stability.

## Files
- `Project_Deliverable_2.ipynb`
- `data/winequality-red-cleaned-project-d1.csv`
- `data/deliverable_2_regression_results.csv`
- `screenshots/` visualizations
