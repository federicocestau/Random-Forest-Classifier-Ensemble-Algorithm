# Random-Forest-Classifier-Ensemble-Algorithm
First of all it is an Ensemble Algorithm. 
Ensemble methods are techniques that create multiple models and then combine them to produce improved results. Ensemble methods in machine learning usually produce more accurate solutions than a single model would.
What category of algorithms does it belong to?
Similar to some other algorithms, Random Forest can handle both classification and regression. 
A quick recap on the difference between classification and regression :
•	With classification, we attempt to predict a class label. In other words, it is used for problems where the output (target variable) takes a finite set of values, e.g., whether it will rain tomorrow or not. Corresponding algorithm: sklearn.ensemble.RandomForestClassifier
•	Meanwhile, regression is used to predict a numerical label. This means your output can take an infinite set of values, e.g., a house price. Corresponding algorithm:sklearn.ensemble.RandomForestRegressor
How does the Random Forest classification algorithm work?
Under the hood, the random forest is essentially a CART algorithm (Classification and Regression Trees), except it creates an ensemble of many trees instead of just one. This provides several advantages such as:
•	Improved performance (the wisdom of crowds)
•	Improved robustness (less likely to overfit since it relies on many random trees)
Random Forest algorithm uses majority agreement prediction for the class label, which means that each tree predicts whether the observation belongs to ‘Class 0’ or ‘Class 1’. If 55 trees out of a hundred predicted ‘Class 1’ and 45 predicted ‘Class 0’, then the final model prediction would be ‘Class 1’. The majority prediction from multiple trees is better than an individual tree prediction because the trees protect each other from their individual errors. This is, however, dependent on the trees being relatively uncorrelated with each other.
In case of regression, each tree is created from a different sample of rows and at each node, a different sample of features is selected for splitting. Each of the trees makes its own individual prediction. These predictions are then averaged to produce a single result.
The following steps will tell you how random forest works:
1.	Create Bootstrap Samples: Construct different samples of the dataset with replacements by randomly selecting the rows and columns from the dataset. These are known as bootstrap samples. Simply put, n random records and m features are taken from the data set having k number of records.
2.	Build Decision Trees: Construct the decision tree on each bootstrap sample as per the hyperparameters.
3.	Individual Outputs: Each decision tree will generate an output.
4.	Final Output: Final output is considered based on Majority Voting or Averaging for Classification and regression, respectively.
This method produces many samples with the same observations but different distributions. In the end, the aggregation of these trees leads to a reduction in the variance of your model prediction, turning it into a low-variance estimator compare to decision trees, CART.
A large number of relatively uncorrelated models (trees) operating as a committee will outperform any of the individual constituent models.
The reason for this wonderful effect is that the trees protect each other from their individual errors (as long as they don’t constantly all err in the same direction). While some trees may be wrong, many other trees will be right, so as a group the trees are able to move in the correct direction. So the prerequisites for random forest to perform well are:
1.	There needs to be some actual signal in our features so that models built using those features do better than random guessing.
2.	The predictions (and therefore the errors) made by the individual trees need to have low correlations with each other.


