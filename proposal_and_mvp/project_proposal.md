#Classification Project Proposal

##Question

- Predict the probability that a driver will initiate a car insurance claim in the next year.
- Inaccuracies in a car insurance company’s claim predictions lead to wrongly-priced insurance premiums.
- This is a problem for the company: it may be uncompetitive and lose business from customers to whom it is charging too much. Meanwhile it may lose money on customers to whom it charges too little.

## Data Description

- The data comes from a Kaggle competition from a few years ago: [Porto Seguro's Safe Driver Prediction](https://www.kaggle.com/c/porto-seguro-safe-driver-prediction/overview)
- Porto Seguro is one of Brazil's largest car and home insurance companies, and for the competition it provided disguised, real commercial data.
- I will use the competition training data only (for the competition test data, the target variable is not publicly available). 
- The training data has 595,212 datapoints - one per driver per year - each with 57 features.
- I will split the competition training data into training/validation and holdout data, with performance on the holdout data giving an indication of how well a given model generalises.
- Because it is commercially sensitive data, the names of the features have been disguised. No information is supplied on what the values relate to in practice.
- The target variable is a boolean field: whether or not an insurance claim was initiated.
 
##Tools

- Google Cloud
- Pandas
- Numpy
- Scikitlearn
- Matplotlib
- Seaborn

## MVP Goal
- A trained logistic regression model with performance metrics
