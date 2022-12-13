# Interpretable machine learning
[Should I Compute Importance on Training or Test Data?](https://christophm.github.io/interpretable-ml-book/feature-importance.html#feature-importance-data)

# Model Interpretation Strategies
## Traditional Techniques for Model Interpretation
[link](https://towardsdatascience.com/explainable-artificial-intelligence-part-2-model-interpretation-strategies-75d4afa6b739)

### Exploratory Analysis and Visualization:
- **Dimensionality reduction:** Principal Component Analysis (PCA), Self-organizing maps (SOM), Latent Semantic Indexing
- **Manifold Learning:** t-Distributed Stochastic Neighbor Embedding (t-SNE)
- **Variational autoencoders:** An automated generative approach using variational autoencoders (VAE)
- **Clustering:** Hierarchical Clustering

### Model Performance Evaluation Metrics
Supervised Learning 
- **Classification:** For classification problems, our main objective is to predict a discrete categorical response variable. The confusion matrix is extremely useful here from which we can derive a whole bunch of useful metrics including accuracy, precision, recall, F1-Score.
- **Regression:** For regression problems we can use standard metrics like the coefficient of determination (R-square), the root mean-square error (RMSE) and the mean absolute error (MAE).  

Unsupervised Learning
- **Clustering:** For unsupervised learning problems based on clustering we can use metrics like the silhouette coefficient, homogeneity, completeness, V-measure and the Calinski-Harabaz index.

Model interpretation (new approaches) of a predictive model — currently in regard to supervised learning problems. 
- Fairness (unbiasedness/non-discriminative), 
- accountability (reliable results), 
- transparency (being able to query and validate predictive decisions) 

### The Accuracy vs. Interpretability Trade-off
In the industry, you will often hear that business stakeholders tend to prefer models which are more interpretable like linear models (linear\logistic regression) and trees which are intuitive, easy to validate and explain to a non-expert in data science. This increases the trust of people in these models since its decision policies are easier to understand.

## Model Interpretation Techniques

### Interpretable Models
The easiest way to get started with model interpretation is to use models which are interpretable out of the box!
- linear regression, 
- logistic regression, 
- tree-based models, 
- rule-fits
- k-nearest neighbors
- Naive Bayes!

A way to categorize these models based on their major capabilities would be:
- **Linearity:** Typically we have a linear model model if the association between features and target is modeled linearly.
- **Monotonicity:** A monotonic model ensures that the relationship between a feature and the target outcome is always in one consistent direction (increase or decrease) over the feature (in its entirety of its range of values).
- **Interactions:** You can always add interaction features, non-linearity to a model with manual feature engineering. Some models create it automatically also.

<img height=200 src="https://miro.medium.com/max/4800/1*ngphhpGUlZMuc6Z6zXnICg.png" />

### Feature Importance
Feature importance is generic term for the degree to which a predictive model relies on a particular feature. Typically, a feature’s importance is the increase in the model’s prediction error after we permuted the feature’s values.
The intuition is that the more a model’s decision criteria depend on a feature, the more we’ll see predictions change as a function of perturbing a feature. However, frameworks like SHAP, use a combination of feature contributions and game theory to come up with SHAP values. Then, it computes the global feature importance by taking the average of the SHAP value magnitudes across the dataset.  


Feature importance is really straightforward:
- We measure a feature’s importance by calculating the increase of the model’s prediction error after perturbing the feature.
- A feature is “important” if perturbing its values increases the model error, because the model relied on the feature for the prediction.
- A feature is “unimportant” if perturbing its values keeps the model error unchanged, because the model basically ignored the feature for the prediction.

The permutation feature importance measurement was introduced for Random Forests by Breiman (2001).  
- YT: [13.4.2 Feature Permutation Importance (L13: Feature Selection)](https://www.youtube.com/watch?v=VUvShOEFdQo&ab_channel=SebastianRaschka)
Dominici (2018) proposed a model-agnostic version of the feature importance — they called it Model Reliance.

It shall be noted that the feature importance values **do not sum up to one**, since they are not normalized (you can normalize them if you'd like, by dividing these by the sum of importance values).

### Partial Dependence Plots
Partial Dependence describes the marginal impact of a feature on model prediction, holding other features in the model constant. The derivative of partial dependence describes the impact of a feature (analogous to a feature coefficient in a regression model). 
- YT: [What it tells us](https://www.youtube.com/watch?v=cmHfEMAJAcM&ab_channel=Dataiku)
- YT: [How it works](https://youtu.be/21QAKe2PDkk?t=45)
  
Some plots with Skater and SHAPE:  
<img height=200 src="https://miro.medium.com/max/4800/1*ThFbVhMWnPRFJ80DpLqdCg.png" />  
<img height=200 src="https://miro.medium.com/max/4800/1*-CV-2hWUXDNk_dslMB6syQ.png" />

### Global Surrogate Models
Intepretable approximations of really complex models.  
A global surrogate model is an interpretable model that is trained to approximate the predictions of a black box model which can essentially be any model regardless of its complexity or training algorithm — this is as model-agnostic as it gets!

Typically we approximate a more interpretable surrogate model based on our base/complex model which is treated as a black box model. We can then draw conclusions about the black box model by interpreting the surrogate model. Solving machine learning interpretability by using more machine learning!

Fitting a surrogate model is a model-agnostic method, since it requires no information about the inner workings of the black box model, only the relation of input and predicted output is used. The choice of the base black box model type and of the surrogate model type is decoupled. Tree-based models are not too simplistic but interpretable and make a good choice for building surrogate models.

Steps:
1. Train a complex model on your dataset (say an nn).
2. Chose an *surrogat model* (linear regression, decision tree).
3. Train the surrogat model on the complex models inputs and prediction (training dataset?).
4. Interpret surrogat model.

### Local Interpretable Model-agnostic Explanations (LIME)
- https://towardsdatascience.com/explainable-artificial-intelligence-part-2-model-interpretation-strategies-75d4afa6b739#:~:text=Local%20Interpretable%20Model%2Dagnostic%20Explanations%20(LIME)

### SHAP (Shapley Values and SHapley Additive exPlanations)
- [Paper](https://dl.acm.org/doi/10.5555/3295222.3295230)
- SHAPE docs: [Decision plots](https://shap.readthedocs.io/en/latest/example_notebooks/api_examples/plots/decision_plot.html)

#### Blogs
- TWD: [Shapley Values and SHapley Additive exPlanations (SHAP)](https://towardsdatascience.com/explainable-artificial-intelligence-part-2-model-interpretation-strategies-75d4afa6b739#:~:text=Shapley%20Values%20and%20SHapley%20Additive%20exPlanations%20(SHAP))
- TWD: [SHAP: Explain Any Machine Learning Model in Python](https://towardsdatascience.com/shap-explain-any-machine-learning-model-in-python-24207127cad7)
- TWD: [Explainable AI (XAI) with SHAP -Multi-Class Classification Problem](https://towardsdatascience.com/explainable-ai-xai-with-shap-multi-class-classification-problem-64dd30f97cea)

#### Videos
- YT: [The Science Behind InterpretML: SHAP](https://www.youtube.com/watch?v=-taOhqkiuIo&ab_channel=MicrosoftDeveloper)


### Sensetivity analysis
‘Sensitivity analysis is the study of how the uncertainty in the output of a model (numerical or otherwise) can be apportioned to different sources of uncertainty in the model input’ -  (Saltelli, 2002).

#### Morris Sensitivity Analysis (or Morris methods)
- Paper: [SALib: An open-source Python library for Sensitivity Analysis](https://joss.theoj.org/papers/10.21105/joss.00097)
- [SALib (Git)](https://github.com/SALib/SALib)
- YT: [Will Usher: Using the SALib library for conducting sensitivity analyses of models](https://www.youtube.com/watch?v=gkR_lz5OptU&ab_channel=PyData)
- Blog: [Morris Sensitivity Analysis](https://interpret.ml/docs/msa.html)


## Tools
- [What-if-tool](https://github.com/pair-code/what-if-tool)


## Resources:
- [H20: Model explainability](https://docs.h2o.ai/h2o/latest-stable/h2o-docs/explain.html#output-explanations)