# Data preprocessing
...

## Target leakage
Target leakage, sometimes called data leakage, is one of the most difficult problems when developing a machine learning model. It happens when you train your algorithm on a dataset that includes information that would not be available at the time of prediction. For instance, using a customer review as a feature for predict if that customer would by a product.

## Training-serving skew
Training-serving skew is a difference between performance during training and performance during serving. This skew can be caused by:
- A discrepancy between how you handle data in the training and serving pipelines.
- A change in the data between when you train and when you serve.


## Missing values

### 3 types of missing data
#### **Missing comletely at random (MCAR):**  
*Missing data is not related to observable variables or unobservable factors.* When data are MCAR, the analysis performed on the data is unbiased; however, data are rarely MCAR. 

#### **Missing at random (MAR):**  
*Missing data corresponds to some observable variable.* MAR is always a safer assumption than MCAR and at least somewhat plausible.

#### **Missing not at random (MNAR):**  
*Missing data is related to some unobservable factor.* For instance a broken sensor.  
When data is MNAR, it means that we cannot use any of the standard methods for dealing with missing data. If the missing data is missing not at random, any standard calculations give the wrong answer.  

It is dangerous to impute or remove samples with missing MNAR data since this can produce a bias in a model.

### Diagnosting missing values
#### MAR vs. MNAR
The only true way to distinguish between MNAR and MAR is to measure some of that missing data. Revisit our population, if their responses on those key items differ by very much, that’s good evidence that the data are MNAR.

#### MCAR vs. MAR
There is a very useful test for MCAR, [Little’s test](https://towardsdatascience.com/statistical-test-for-mcar-in-python-9fb617a76eac). But like all tests of assumptions, it’s not definitive. So run it, but use it as only one piece of information.  
A second technique is to create dummy variables for whether a variable is missing and run t-tests and chi-square tests between this variable and other variables in the data set to see if the missingness on this variable is related to the values of other variables.

**Resources:**
1. [What are the Different Types of Missing Data?](https://www.displayr.com/different-types-of-missing-data/#_edn1)
2. [how to diagnose the missing data mechanism](https://www.theanalysisfactor.com/missing-data-mechanism/)
3. [9.2 MCAR, MAR, MNAR - Introduction to Regression Methods for Public Health Using R](https://bookdown.org/rwnahhas/RMPH/mi-mechanisms.html#mi-mechanisms)

### Handling missing data
There are three ways to handle missing data: *Omission* - removing samples with missing data or compleate features, Imputation - calculate the missing values, or *Analysis* - use methods unaffected by missing data.

#### Omission
...  
Listwise deletion, however, requires the data are MCAR in order to not introduce bias in the results.

#### Imputation
...  
One approach is to assume the data are MAR and use MI to handle the missing data.


## Handeling data dstribution
### Skew distribution
The identified problem is that the distribution of the numeric attribute exhibits a long-tail shape.  

*"When" is it considered skewed (threshold)?*

#### How to handle skewed distribution
- Sometimes outliers can originate from incorrect data, in which case an understanding of the source of the error may allow changing the outlier value with a plausible one.
- If extreme values cannot be treated as outliers, transformations (such as log transformations) are usually recommended to generate a more balanced distribution.
- Another transformation technique for handling the skew distribution is bucketization or binning. Bucketizing the numerical feature so that the number of data points in each bucket or bin is balanced can effectively mitigate the
skew and preserve the predictive power. This is also called equal-frequency binning. There are other binning strategies (for example, equal-width binning) that cannot resolve the skew.
- In certain cases, the extreme values are actually caused by outliers. Filtering out the extreme values or outliers would bring the distribution of the attribute back to normal. It is important to note that outlier removal should be applied consistently to both training and serving. There are two typical methods for removing the outliers:
  - Clipping the attribute at a computed percentile (for example, 99%), assuming that the majority of the data is valid and only a small percent (for example, 1%) is abnormal.
  - Filtering by fixed threshold, if it is known that there is a normal value range for the numerical attribute (for example, the latitude and longitude).







## Resources



## Google's AutoML data preprocessing and transformation
- [Data preparation best pratics](https://cloud.google.com/automl-tables/docs/data-best-practices#data_preparation_best_practices)
- [Exploratory Data Analysis for Feature Selection in Machine Learning](https://services.google.com/fh/files/misc/exploratory_data_analysis_for_feature_selection_in_machine_learning.pdf)

### Blogs: 
- [About Feature Scaling and Normalization](https://sebastianraschka.com/Articles/2014_about_feature_scaling.html#z-score-standardization-or-min-max-scaling)
- [Labeling, transforming, and structuring training data sets for machine learning with Snorkel](https://medium.com/@harrison.miller13_28580/labeling-transforming-and-structuring-training-data-sets-for-machine-learning-with-snorkel-d4813e2aad74)
- [DATA CLEANING IS A MACHINE LEARNING PROBLEM THAT NEEDS DATA SYSTEMS HELP!](https://wp.sigmod.org/?p=2288)

## PAper
### Tidy data
http://vita.had.co.nz/papers/tidy-data.html