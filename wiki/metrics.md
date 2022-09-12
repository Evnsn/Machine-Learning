# Metrics
...

## Regression metrics
There are many metrics for regression. You can see the full list of regression metrics supported by the scikit-learn Python machine learning library here: [Regression Metrics](https://scikit-learn.org/stable/modules/classes.html#regression-metrics).

### Mean Squared Error (MSE)
MSE represents the average of the squared difference between the original and predicted values in the data set. It measures the variance of the *residuals* (difference between an observed and the predicted value)  

$$ \LARGE{MSE = \frac{1}{N} \sum_{i=1}^{N}(y_{i} - \hat{y_{i}})^{2}}. $$

**Pros:** 
- MSE penalizes the large prediction errors.
- MSE is a differentiable function (derivative exists at each point in its domain), in c.


### Root Mean Squared Error (RMSE)
Root Mean Squared Error is the square root of MSE. It measures the standard deviation of residuals  

$$ \LARGE{RMSE =\sqrt{ \frac{1}{N} \sum_{i=1}^{N}(y_{i} - \hat{y_{i}})^{2}} }. $$

**Pros:**
- RMSE tells how well a regression model can predict the value of a response variable in absolute terms.

### Mean Absolute Error (MAE)
MAE represents the average of the absolute difference between the actual and predicted values in the dataset. It measures the average of the residuals in the dataset  

$$ \LARGE{MSA = \frac{1}{N} \sum_{i=1}^{N}|y_{i} - \hat{y_{i}}|}. $$

## Goodness of fit
- [wikipedia](https://en.wikipedia.org/wiki/Goodness_of_fit)
