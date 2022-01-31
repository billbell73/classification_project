# Classification Module Project

## Car Insurance Claim Prediction

### Abstract

The goal here is to predict the probability that a driver will initiate a car insurance claim in the next year, using the relatively large Porto Seguro Kaggle Competition training dataset. Using ROC AUC value on validation data as the main selection criteria I evaluated the following models: logistic regression with balanced class weights, decision tree, random forest and XGBoost. Generally the predictive power of the models on this dataset was relatively poor. However, XGBoost was the clear winning model. I spent significant time attempting to manually tune the XGBoost model using the early stopping technique with high n_estimators. This had some success but not as much as I expected. I devised a profit function with assumed relevant figures, as a way of choosing a decision probability threshold to split the drivers into two groups for the purposes of profit maximisation via price discrimination. 

### Recorded Presentation

Please see project presentation [here](https://www.youtube.com/watch?v=ocSwE6_UJss).

### Data
- Porto Seguro, a large Brazilian car insurance company, provided a relatively large, real commercial dataset to Kaggle as part of a competition a few years ago.
- The training data they provided has 595,212 datapoints, one per driver per year, each with 57 features; plus a binary target value denoting whether or not a claim was submitted by that driver.
- The data is unbalanced with 21,694 (3.64%) of the datapoints showing a claim.
- The feature names and values are disguised so we do not know what any of the features actually relate to.

### Algorithms
- Logistic Regression with balanced class weights
- Decision Tree
- Random Forest
- XGBoost

I was surprised that significant tuning effort improved the winning XGBoost model only marginally. I used the approach recommended in the `GradientBoostedTrees_xgboost.ipynb` course download: i.e. using a manual tuning procedure (the reasonably large dataset meaning grid search was prohibitively slow) and using the early stopping technique with n_estimators set to a very large number. 

The fact the model was a little better on the validation data that on the holdout data (AUC scores of 0.645 and 0.641 respectively) implies the model was somewhat overfit. With more time I would like to combine early stopping with k-fold cross validation to combat this.

### Profit function

I found it a bit of a challenge to come up with a profit function that made sense in the context of this project. Price discrimination usually works by enabling a company to reach more customers. But I didn't want to invent a demand curve - i.e. how many more customers would be reached with a lowered price - because that seemed too speculative and off-topic. Therefore I came up with the (possibly slightly convoluted?) scenario of a fixed price for one group and a fixed markup / profit per policy for the other group. As can be seen from the presentation appendix, I tried to find a realistic figure for average payout per car insurance claim via the [Insurance Information Institute](https://www.iii.org/fact-statistic/facts-statistics-auto-insurance)

### Tools

* Compute: I tried two methods of using Jupyter in the cloud, namely using a Google Cloud VM and Google Colab
* Data storage: .csv file and Python Pickle
* EDA: Python Pandas
* Modelling: Sklearn
* Visualizations: matplotlib, Seaborn, Plotly


### Communication
The methodology and results of this project have been communicated via this document, and via a [recorded presentation](https://www.youtube.com/watch?v=ocSwE6_UJss) and its [slide-deck](https://github.com/billbell73/classification_project/blob/main/project_presentation.pdf).
