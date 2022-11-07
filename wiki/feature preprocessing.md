# Feature preprocessing

## Data Discretization

### Blog: 
[Medium - Data Discretization](https://medium.com/codex/data-discretization-b5faa2b77f06)


## Feature engineering
https://towardsdatascience.com/feature-engineering-for-machine-learning-3a5e293a5114

### A Reference Guide to Feature Engineering Methods
https://www.kaggle.com/code/prashant111/a-reference-guide-to-feature-engineering-methods/notebook

### Resources:

#### Blogs:


#### Papers:
- (2017) [Learning Feature Engineering for Classification](https://www.ijcai.org/proceedings/2017/0352.pdf)

## Feature selection

### Feature selection based on descriptive analysis
The following are indicators of problematic features:

#### High percentage of missing values
The attribute is missing in a significant proportion of the data points. The threshold can be set based on business domain knowledge.  
There are two options to handle this, depending on the business scenario:
- The missing value, in certain contexts, is actually meaningful. For example, a missing value could indicate that a monitored, underlying process was not functioning properly. Therefore, assigning a unique value to the missing valuerecords is a reasonable way to handle the situation.
- A value can be missing due to misconfiguration, issues with data collection, or untraceable random reasons, in which case the feature can simply be discarded if the historic data cannot be reconstituted.

#### Low variance of numeric attributes
The identified problem is a very small variance of the feature compared to the typical value range of the feature, or the distribution is a sharp bell curve. In most cases, it is safe to remove numeric attributes with low
variance.

#### Low entropy of categorical attributes
The identified problem is a very small entropyof the feature, which means that most of the records have the same categorical values. In most cases, it is safe to remove categorical attributes with low entropy.

#### High cardinality
The identified problem occurs when the number of unique values is too large for categorical attributes. This high cardinality creates problems for the typical one-hot-encoding process, creating a representation in an extremely
high-dimensional space. Such high dimensionality often follows if the agent (user or item) ID is used as the feature.  
The typical remedy for this would be:
- Removing the feature if the number of occurrences per unique value of the attributes is too low (for example, less than 5).
- Applying a [hash trick](https://en.wikipedia.org/wiki/Feature_hashing), which converts a high cardinality categorical attribute to a fixed sized one-hot-encoded space.
- Embedding, a mapping from discrete objects, such as words, to vectors of real numbers.




### Resources
Google's guid: https://services.google.com/fh/files/misc/exploratory_data_analysis_for_feature_selection_in_machine_learning.pdf

- Low variance / entropy
- Highly correlated data

Sklearning: https://scikit-learn.org/stable/modules/feature_selection.html

### Resources:

#### Blogs 
- [TWDS](https://towardsdatascience.com/beginners-guide-for-feature-selection-by-a-beginner-cd2158c5c36a)
- [Motivations for feature preprocessing](https://neptune.ai/blog/feature-selection-methods)
- [ML Mastery](https://machinelearningmastery.com/feature-selection-with-real-and-categorical-data/)
  - I would personally stick to pearson/spearmans for numerical and chi squared for categorical

#### Papers:
- (2018) [On the Stability of Feature Selection Algorithms](https://www.jmlr.org/papers/volume18/17-514/17-514.pdf)
  


 


 