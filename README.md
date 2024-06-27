### R project

#### Dataset: 
https://kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions. It contains only numeric input variables which are the result of a PCA transformation. Due to confidentiality issues, the original features are not provided. Features V1, V2, … V28 are the principal components obtained with PCA. The other features provided are Time and Amount. The target feature is Class (non-fraudulent and fraudulent)
#### Data Analysis: <br>
- There are no missing values.
- The dataset is heavily imbalanced with 99.8% of cases being non-fraudulent transactions.
- Accuracy cannot be used, so I’ve used AUC instead to measure the model performance.
- Variance in non-fraudulent transactions is much more than fraudulent transactions. 
- Since, the features V1 to V28 are a result of PCA, they don’t have much correlation.
- t-SNE with perplexity set to 20 shows separation between 2 classes.
#### Modelling: <br>
- Up-sampling is used to handle class imbalance. This decision is made using AUC on an imbalanced dataset, downsampled, and upsampled dataset.
- XGBOOST is used for fitting and prediction
- Most important features are V14, V10, V4, V17, V11, V12, V3, V13, V26, V19 in descending order.
