# Metrics
test

## Regression metrics
There are many metrics for regression. You can see the full list of regression metrics supported by the scikit-learn Python machine learning library here: [Regression Metrics](https://scikit-learn.org/stable/modules/classes.html#regression-metrics).

### Mean Absolute Error (MAE)
MAE represents the average of the absolute difference between the actual and predicted values in the dataset. The lower value implies higher accuracy. It measures the average of the residuals in the dataset  

$$ \LARGE{MSA = \frac{1}{N} \sum_{i=1}^{N}|y_{i} - \hat{y_{i}}|}. $$

**Pros:** 
- MAE is easy to interpret.
- All of the errors will be weighted on the same linear scale. Unlike the MSE, we won’t be putting too much weight on our outliers and our loss function provides a generic and even measure of how well our model is performing.
- MAE is greate for ignoring outliers.

**Cons:**
- If we do in fact care about the outlier predictions of our model, then the MAE won’t be as effective.
- Not differentiable.

### Mean Squared Error (MSE)
MSE represents the average of the squared difference between the original and predicted values in the data set. The lower value implies higher accuracy. It measures the variance of the *residuals* (difference between an observed and the predicted value)  

$$ \LARGE{MSE = \frac{1}{N} \sum_{i=1}^{N}(y_{i} - \hat{y_{i}})^{2}}. $$

**Pros:** 
- MSE penalizes the large prediction errors, in contrast to MAE.
- MSE is a differentiable function (a function whose derivative exists at each point in its domain), in contrast to MAE.
- MSE is great for learning outliers.

**Cons:**
- Outliers have a large impact on the error estimation.


### Root Mean Squared Error (RMSE)
Root Mean Squared Error is the square root of MSE. The lower value implies higher accuracy. It measures the standard deviation of residuals  

$$ \LARGE{RMSE =\sqrt{ \frac{1}{N} \sum_{i=1}^{N}(y_{i} - \hat{y_{i}})^{2}} }. $$

**Pros:**
- RMSE penalizes the large prediction errors, in contrast to MAE.
- RMSE is a differentiable function (a function whose derivative exists at each point in its domain), in contrast to MAE.
- RMSE tells how well a regression model can predict the value of a response variable in absolute terms.


### Huber Loss
[link](https://bigdatafinance.tw/index.php/tech/methodology/897-3-most-common-loss-functions-for-machine-learning-regression)

### R Squared 
...

### Adjusted R Squared 
...


## Classification metrics
...


## Goodness of fit
- [wikipedia](https://en.wikipedia.org/wiki/Goodness_of_fit)
