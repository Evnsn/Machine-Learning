# Imbalanced datasets
...

## SMOTE (Synthetic Minority Oversampling Technique) - Oversampling
[Paper (2002)](https://arxiv.org/abs/1106.1813#:~:text=An%20approach%20to%20the%20construction,are%20not%20approximately%20equally%20represented.)  

SMOTE is a data augmentation method used as a *oversampling technique* to solve imbalanced dataset problem. It creats syntetic data of the minority class by selecting instances that are close in feature space, draws a line between the instances and adds a new instance somewhere along that line.  

### SMOTE algorithm:
1. Take a sample of the minority class from the dataset, and consider its k nearest neighbors (in feature space). 
2. To create a synthetic data point, take the vector between one of those k neighbors, and the current data point.
3. Select randomly select a point between the two datapoints.

<img height=300 src="https://editor.analyticsvidhya.com/uploads/77417image1.png" />

### Pros and cons:
**Pros:**
- The combination of SMOTE and under-sampling performs better than plain under-sampling.
- Can interpolate as many sythetic datapoints as needed.

**Cons:**
- A general downside of the approach is that synthetic examples are created without considering the majority class, possibly resulting in ambiguous examples if there is a strong overlap for the classes.

#### Resources:
- Machine learning mastery: [SMOTE for Imbalanced Classification with Python](https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/).
- Geeks for geeks: [Handling Imbalanced Data with SMOTE and Near Miss Algorithm in Python](https://www.geeksforgeeks.org/ml-handling-imbalanced-data-with-smote-and-near-miss-algorithm-in-python/)
- Analytics Vidhya: [Overcoming Class Imbalance using SMOTE Techniques](https://www.analyticsvidhya.com/blog/2020/10/overcoming-class-imbalance-using-smote-techniques/)
- Wikipedia: [Oversampling and undersampling in data analysis](https://en.wikipedia.org/wiki/Oversampling_and_undersampling_in_data_analysis#SMOTE)