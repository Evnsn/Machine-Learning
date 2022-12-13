# EDA
...

## Statistical data analysis
The exploration of the data is conducted from three different angles: descriptive, correlative, and contextual. 

### 1. Descriptive analysis (univariate analysis)
Descriptive analysis provides an understanding of the characteristics of each attribute/feature of the dataset. It also offers important evidence for feature selection in a later state. 

*Note:* The statistics that follows and in general, exclude the detected missing values.

#### Common:
- Data type: Attribute's data type; Numerical, categorical or text.
- Missing values: Precentage of missing values.

#### Numerical:
- Quantile statistics: Q1, Q2, Q3, min, max, range, interquartile range
- Descriptive statistics: Mean, mode, standard deviation, median
absolute deviation, kurtosis, skewness
- Distribution histogram: Based on the appropriate number of bins

#### Categorical:
- Cardinality:  Number of unique values for the categorical attribute
- Unique counts: Number of occurrences for each unique value of the categorical attribute

#### Textual:
- Tokens: Number of unique tokens
- DF/TF: Distribution of document frequency and term frequency with or without stop words


### 2. Correlation analysis (bivariate analysis)
Correlation analysis (or bivariate analysis) examines the relationship between two attributes, and determines whether the two are correlated. 

#### 2.1 Qualitative analysis:
Computing of the descriptive statistics of dependent numerical or categorical attributes against each unique value of the independent categorical attribute.

##### Numerical vs Numerical/Categorical:  
Scater plot

###### Categorical vs Categorical:   
Contingence table with unique counts of the independent variable per unique value of the dependent variable.

###### Categorical vs Numerical:  
Descriptive statistics or histogram of the dependent variable per unique value of the independent variable.

#### 2.2 Qualitative analysis:
Quantitative analysis quantifies relationships by generating numerical data or data that can be
transformed into usable statistics. In the case of correlation analysis, the quantitative analysis
is done through a statistical hypothesis test.

#### 2.3 Contextual analysis
To gain more domain-specific insights, two generic contextual information-based analyses are recommended: *time based* and *agent based*.

##### Time-based analysis
In many real-world datasets, the timestamp (or similar time-related attributes) is one of the key pieces of contextual information.

With the timestamp attribute, the following analyses could be performed:
- *Number of records* (transactions) per time interval
  - For example, hourly pageviews for a website
- *Number of unique values* (of an attribute) per time interval
  - For example, hourly unique visitors to a website
- *Descriptive statistics* per time interval
  - For example, the daily average session duration for a website

##### Agent-based analysis
As an alternative to the timestamp, another common attribute is a unique identification. May be used to capture user activity.


# AutoEDA Libraries:
- Pandas Profiling
- SweetViz
- AutoViz
- LUX
- D Tale
- DataPrep

# Piviot tabel
https://towardsdatascience.com/5-minute-guide-to-pandas-pivot-tables-df2d02786886


# Pandas direct plots
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.html#pandas.DataFrame.plot


## Resources:
- ...
- [Understanding Feature Importance and How to Implement it in Python](https://towardsdatascience.com/understanding-feature-importance-and-how-to-implement-it-in-python-ff0287b20285)

## Tools:
- GiT: [List of Python libaries](https://github.com/topics/visualization?l=python)