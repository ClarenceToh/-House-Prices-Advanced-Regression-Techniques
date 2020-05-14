# Description of Kaggle Competition
https://www.kaggle.com/c/house-prices-advanced-regression-techniques/
Predict sales prices and practice feature engineering, RFs, and gradient boosting

# housing regression1.ipynb
### Objective
An intitial regression model for perdicting sale prices of houses, given a dataset of characteristics.
### The Kaggle Platform
This code serves to be an introduction to beginners who may want to participate in a kaggle competition using google colab.
### Data Cleaning 
1. Check datatype of each column<br />
2. Check for missing data<br />
3. Combine both train and test set for data preparation<br />
4. Remove columns with more than 20% missing data (Set threshold)<br />
5. For columns with missing data (dtype int / float), fill with the median (or mean)<br />
6. For columns with missing data (dtype object), impute with most frequent value<br />

### Data Preparation
1. Check for missing data once more<br />
2. Drop any duplicate rows<br />
3. Perform one hot encoding for dtype object column values<br />
4. Split train and test set<br />
5. Within the train set, split into training and validation set<br />

### Regression
For experimentation, run the training set on multiple models from sklearn.<br />
Get an idea of what are the best performing models. I used Root Mean Squared Log Error and R2 Scores for evaluation<br />
In both cases, Random Forest Regressor performs the best.<br />
after which, i tried a couple of things.<br />
First, I did minmax and standard scaling. None improved the score.<br />
Second, I did feature dimensionality reduction via Principal Component Analysis. Still was not better.<br />
Ultimately, after the first iteration, the socre was 0.15006, where I was ranked 2535 out of 4524 teams, which is not impressive.<br />
This is the preliminary model. I will continue to work on the regression model to improve the score.<br />

# housing regression1.ipynb
### Objective
To improve the compeition score in the second iteration.

### Main Changes
1. Having prepared the dataset to numerize all object type data and cleaning the rest of the integer type data, there was 1000 estimators involved. Hence, I tuned the parameter n_estimator of the best performing model, the RandomForstRegressor, to 1000. The score improved from 0.15 to 0.14.
2. Next, I decided to try XGBoost again despite it not being the best in the first iteration. This time I tuned the n_estimator parameter to 1000 and the score drastically improved. The RMSLE reduced to 0.12980 in the competition which stands as the best score so far.
3. I was still skeptical. I tuned and optimised the parameters, colsample_bytree, learning_rate, subsample and max_depth. It generated the best test score, but the competition score was not better than 0.12980

### Next Step
I will implement feature extraction/ feature importance to see what features are most important. The hypothesis is that not all factors affect the prices of houses the same, so identifying which estimators affect the target variable the most will be kept.

Probably some neural networks will be implemented as well.
