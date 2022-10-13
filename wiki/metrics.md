# Metrics

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
- MSE effectively penalizes larger errors more severely, in contrast to MAE.
- MSE is a differentiable function (a function whose derivative exists at each point in its domain), in contrast to MAE.
- MSE is great for learning outliers.

**Cons:**
- Outliers have a large impact on the error estimation.


### Root Mean Squared Error (RMSE)
Root Mean Squared Error is the square root of MSE. RMSE tells how well a regression model can predict the value of a response variable in absolute terms.  It measures the standard deviation of residuals. The lower value implies higher accuracy

$$ \LARGE{RMSE =\sqrt{ \frac{1}{N} \sum_{i=1}^{N}(y_{i} - \hat{y_{i}})^{2}} }. $$

**Pros:**
- RMSE effectively penalizes larger errors more severely, in contrast to MAE.
- RMSE tells how well a regression model can predict the value of a response variable in absolute terms.
- We use the RMSE more often because it is measured in the same units as the response variable. Conversely, the MSE is measured in squared units of the response variable.
- RMSE is a differentiable function (a function whose derivative exists at each point in its domain), in contrast to MAE.
- When used as a loss function, easy to compute gradient.
- For comparing the accuracy among different linear regression models, RMSE is a better choice than R Squared.

**Cons:**
- Hard to interpret.
- Need to compare with other models RMSE to check if this RMSE is good/bad.

### Huber Loss
[link](https://bigdatafinance.tw/index.php/tech/methodology/897-3-most-common-loss-functions-for-machine-learning-regression)

### R-Squared ($R^{2}$) 
$R^{2}$, also known as *Coefficient of determination* represents the proportion of the variance in the dependent variable which is explained by the linear regression model 

$$ \LARGE{R^2} = 1 - \frac{RSS}{TSS} = 1 - \frac{\Sigma{(y-\hat{y})^{2}}}{(y-\bar{y})^{2}}. $$

*RSS - 	sum of squares of residuals*, *TSS - total sum of squares*, *$\bar{y}$ - mean value of $y$*.  
$R^{2}$ is usually between 0 and 1 and idicates how much of the variation your model is able to account for in your data.


**Pros:**
- $R^{2}$ can be more (intuitively) informative than MAE, MSE, and RMSE in regression analysis evaluation.
- $R^{2}$ tells how well the predictor variables can explain the variation in the response variable
- Don’t need to compare with other model, value tell you whether it’s good or bad.
- Models that have worse predictions than this baseline will have a negative $R^{2}$.

**Cons:**
- $R^{2}$ cannot determine whether the coefficient estimates and predictions are biased.
- Adding a independent variables will ALWAYS increase the $R^{2}$ score.
- When evaluating the goodness-of-fit of simulated vs. measured values, it is not appropriate to base this on the  of the linear regression


### Adjusted R Squared 
...


**Pros:**
- Adjusted R squared takes into account the number of predictor variables, and it is used to determine the number of independent variables in our model. The value of Adjusted R squared decreases if the increase in the R square by the additional variable isn’t significant enough.

**Cons:**
- 

### RMSLE
...

### MAPE
...

## Classification metrics

### Accuracy
...

### Recall
...

### Precision
...

### F1 score
...

### Micro, macro and weighted
https://datascience.stackexchange.com/questions/15989/micro-average-vs-macro-average-performance-in-a-multiclass-classification-settin

## Goodness of fit
- [wikipedia](https://en.wikipedia.org/wiki/Goodness_of_fit)

## Matthews correlation coefficient (MCC)
- https://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-019-6413-7