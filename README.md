# Startup-selection-to-invest-using-ML-model

Selecting the best startup to invest by analyzing the profit and its expense in different fields using the Multiple Linear Regression

## Dataset

The dataset consists the data of 50 startups and their R&D spend, Administration Spend, Marketing Spend, which state they belong to and the overall profit of certain year.

## Problem

Suppose, one venture capital firm wants to invest in some of the startups but are confused on which one to invest. Well, if we look at the profit only, its obvious that the higher the profit the better one but they want to know the correlation of the most spend to the profit.

## Solution

Multiple Linear Regression is used to predict the right fit or to know the best correlation. Among the different methods of building the model, Backward Elimination is being used.

Encoding the categorical data, avoiding the dummy variable trap and splitting the data (80/20) is done. After that, MLR is fitted to the training set is done and the test set is used to predict. The prediction shows good result as it matches almost the profit as projected.

But our task is to find the most correlated variable with profit. For that an optimal model using Backward Elimination is built. The significance level threshold (P value) is assumed to be 5% (0.05)

The following figure shows the stepwise Backward Elimination process taken until the P value drops below 0.05

OLS Regression result with all the variables.
![OLS Regression Result 1](https://user-images.githubusercontent.com/14214659/71067927-2a730b80-217e-11ea-9283-97fc943929ae.png)


OLS Regression result after removing the variable with the highest P value (dummy variable)
![OLS Regression Results 2](https://user-images.githubusercontent.com/14214659/71068119-aa997100-217e-11ea-8bb0-19d2406a2014.png)


OLS Regression result after removing the variable with the highest P value (also the dummy variable)
![OLS Regression Results 3](https://user-images.githubusercontent.com/14214659/71068456-73778f80-217f-11ea-9efe-df59d1c9a05b.png)


OLS Regression result after removing the variable with the highest P value (Administration spend)
![OLS Regression Results 4](https://user-images.githubusercontent.com/14214659/71068571-ac176900-217f-11ea-895d-4878b1cc8075.png)


OLS Regression result after removing the variable with the highest P value (Marketing spend)
![OLS Regression Results 5](https://user-images.githubusercontent.com/14214659/71068634-ccdfbe80-217f-11ea-9bfd-ba3607d98185.png)


Well, from the above observation one may think that as in the last step of Backward Elimination, we have one strong variable left that is R&D Spend and blindly make conclusion that it is the only one that has most impact on profit (coefficient is 0.8543).

But, well while predicting such results we must just not rely on coefficient, we have to look at the Adjusted R-squared value as the more it is close to 1 the best it is. From the figure it shows that the the Adjusted R-squared value is slightly dropped on the last one compared to the earlier one. Meaning, the adjusted R-squared value is best when the two variables R&D spend and Marketing are taken in account.

## Conclusion

So, we can conclude from that OLS Regression that, the R&D Spend and Marketing spend are the two variables a VC firm must look at when funding the startup. It shows that one unit increase in R&D spend will drive 0.79 units in profit and one unit increase in Marketing spend will drive 0.0299 units in profit. Although, comparatively, R&D spend overrules the Marketing spend, it would be wise for VC firm to take both of these variables into account while making decisions.
