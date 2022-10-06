# Endembling methods
Ensemble modeling is a process where multiple diverse models are created to predict an outcome. This is achieved either by using many different modeling algorithms or using different samples of training data sets. The motivation for using ensemble models is to reduce the generalization error of the prediction. As long as the base models are diverse and independent, the prediction error of the model decreases when the ensemble approach is used.  

  There are different types of Ensemble Learning techniques which differ mainly by the type of models used (homogeneous or heterogeneous models), the data sampling (with or without replacement, k-fold, etc.) and the decision function (voting, average, meta model, etc).

The two most common methods in ensemble learning are *Bagging* and *Boosting*. Some other methods are; *Stacking*, *Voting*, *Blending*,
- [Ref](https://nbviewer.org/github/pycaret/pycaret/blob/master/tutorials/Binary%20Classification%20Tutorial%20Level%20Intermediate%20-%20CLF102.ipynb)

## Bagging and Boosting
<img height=300  src="https://pluralsight2.imgix.net/guides/81232a78-2e99-4ccc-ba8e-8cd873625fdf_2.jpg"></img>

### Bagging
Bagging methods form a class of algorithms which build several instances of a black-box estimator on random subsets of the original training set and then aggregate their individual predictions to form a final prediction. These methods are used as a way to reduce the variance of a base estimator (e.g., a decision tree), by introducing randomization into its construction procedure and then making an ensemble out of it. In many cases, bagging methods constitute a very simple way to improve with respect to a single model, without making it necessary to adapt the underlying base algorithm. As they provide a way to reduce overfitting, bagging methods work best with strong and complex models (e.g., fully developed decision trees) reducing theire variance.  

Bagging methods come in many flavours but are similar in the way they draw random subsets of the training set.
- [Ref](https://scikit-learn.org/stable/modules/ensemble.html#bagging-meta-estimator)

### Boosting
Boosting is a technique that consists in fitting sequentially multiple weak learners in a very adaptative way: each model in the sequence is fitted giving more importance to observations in the dataset that were badly handled by the previous models in the sequence. Intuitively, each new model focus its efforts on the most difficult observations to fit up to now, so that we obtain, at the end of the process, a strong learner with lower bias.  

Boosting methods which usually work best with weak models (e.g., shallow decision trees) reducing there bias.

## Stacking
Stacking is a ensemble learning method that combine multiple machine learning algorithms via meta learning. In which base level algorithms are trained based on a complete training data-set. The meta model is trained on the final outcomes of the all base level model as feature.

<img height=300 src="https://miro.medium.com/max/640/0*TxRot7hP9IRNccqO.png" />

The architecture of a stacking model involves two or more base models, often referred to as level-0 models, and a meta-model that combines the predictions of the base models, referred to as a level-1 model.

- **Level-0 Models (Base-Models):** Models fit on the training data and whose predictions are compiled.
- **Level-1 Model (Meta-Model):** Model that learns how to best combine the predictions of the base models.

The most common approach to preparing the training dataset for the meta-model is via k-fold cross-validation of the base models, where the out-of-fold predictions are used as the basis for the training dataset for the meta-model.

### Stacking Methods:
- Voting
  - Averaging
  - [Weighted Averaging](https://machinelearningmastery.com/weighted-average-ensemble-with-python/)
- [Blending](https://machinelearningmastery.com/blending-ensemble-machine-learning-with-python/)

### Blending
Blending is a technique derived from Stacking Generalization. The only difference is that in Blending, the k-fold cross validation technique is not used to generate the training data of the meta-model. Blending implements “one-holdout set”, that is, a small portion of the training data (validation) to make predictions which will be “stacked” to form the training data of the meta-model. Also, predictions are made from the test data to form the meta-model test data.

### Stacking vs blending
<div style="display:flex; gap:10px;">
    <img height=300 src="https://miro.medium.com/max/720/1*CoauXirckomVXxw2Id2w_Q.jpeg" />
    <img height=300 src="https://miro.medium.com/max/720/1*T0L64nrOJSr8-LRJlWfLtQ.jpeg" />
</div>

**Blending:**  
Stacking-type ensemble where the meta-model is trained on predictions made on a holdout dataset.  

**Stacking:**  
Stacking-type ensemble where the meta-model is trained on out-of-fold predictions made during k-fold cross-validation.

## AdaBoosting
...

## Gradient tree boosting