# MSCS 634 Lab 4: Regression Analysis with Regularization Techniques

This lab uses the Diabetes dataset from `sklearn.datasets` to compare several regression models. The notebook includes simple linear regression, multiple regression, polynomial regression, Ridge regression, and Lasso regression. Each model is evaluated with MAE, MSE, RMSE, and R2.

## Key Insights

The simple linear regression model using BMI gives a useful starting point, but it does not capture enough information from the dataset. The multiple regression model performs better because it uses all available health measurements. Polynomial regression shows how increasing model complexity can lead to overfitting, especially when the training score improves but the test score does not. Ridge and Lasso regularization help control model complexity by shrinking coefficients. Lasso can also make some coefficients zero, which makes the model easier to interpret.

## Challenges and Decisions

One decision was choosing BMI for the simple linear regression model because it has a clear relationship with the target. Another decision was testing several alpha values for Ridge and Lasso instead of using only one value. This made it easier to see how regularization strength changes model behavior. The dataset did not have missing values, so no cleaning step was needed beyond checking the data carefully.
