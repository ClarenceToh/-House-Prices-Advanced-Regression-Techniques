# Description of Kaggle Competition
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
