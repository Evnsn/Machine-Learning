# Dictionary

## Correlation
Correlation is a statistical measure that expresses the extent to which two variables are linearly related.
Correlation, is constrained to be between –1 and 1, whereas covariance
scale depends on the scale of the variables x and z.
$$
    Cor(x,y) = \frac{\sum{(x_i-\overline{x})(y_i-\overline{y})}}{\sqrt{\sum{(x_i-\overline{x})}\sum{(y_i-\overline{y})}}} = \frac{Cov(x,y)}{\sigma_x \sigma_y}
$$

## Covariance
Covariance measures the direction of the relationship between two variables.
Covariance scale depends on the scale of the variables x and z, unlike Correlation which is constrained between –1 and 1.
* The main idea behind covariance is that it can classify three types of relation between variables, *positive*, *negative* or *non*. 
* Covariance is not intresting in itself,  but works as a steping stone for other computations like *Correlation* or *PCA*.
$$
    Cov(x,y) = \frac{\sum{(x_i-\overline{x})(y_i-\overline{y})}}{N-1}
$$

## Distributed representation:  
Distributed representation is a compact dense vector representing an object created a with neural networks. Distributed representation for symbolic data was introduced by Hinton (1985).

## Discrimative models:
Discriminative models draw boundaries in the data space. A discriminative model focuses on predicting the labels of the data.

## Generative models:
Generative models try to model how data is placed throughout the space. A generative model focuses on explaining how the data was generated.

## Heterogeneous:  
*Stacking* often considers heterogeneous weak learners, learns them in parallel, and combines them. In other words; it use different base learning algorithms to directly ensure ensemble diversity.

## Heterogeneous data: 
Data with large variation. For example, patients are typically a very heterogeneous population as they differ with many factors including demographics, diagnostic test results, and medical histories.

## Homogenous:  
A data set is homogeneous if it is made up of things that are similar to each other.  
*Bagging* and *boosting* used homogenous weak learners for ensemble.

## Representation learning:  
Representation learning aims to learn representations of rawdata as useful information for further classification or prediction. Some methds are; *K-mean clustering*, *PCA* and *ICA*.  
*Distributed representation* is also form of representation learning made with neural networks.

## Likelihood:
Likelihood specifically refers to the where we're trying to find the optimal parameters of for a distribution.

### What is the difference between "likelihood" and "probability"?
- StackExchange: [What is the difference between "likelihood" and "probability"?](https://stats.stackexchange.com/questions/2641/what-is-the-difference-between-likelihood-and-probability)
- YT: StatQuest - [Probability is not Likelihood. Find out why!!!](https://www.youtube.com/watch?v=pYxNSUDSFH4&ab_channel=StatQuestwithJoshStarmer)