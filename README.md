# Predicting-Loan-Outcomes

In this project, I predict whether or not a loan will be repaid based on various attributes of the borrower. The data set used for training and prediction is taken from Lending Club.

Since the dataset contains a significant amount of information, I begin by cleaning the data set to remove columns which leak information about the future, which are irrelevant to the borrower's ability to pay back a loan, and which contain redundant information. I also identify columns which need to be transformed in order to be useful.

After data cleaning, I transform the data in the target column to make the problem one of binary classification. I then alter data in other columns so that they contain categorical, rather than continuous, data. Finally, I deal missing values in the remaining columns by either removing rows or replacing the missing value with the column mean.

Once the data is suitable for use in machine learning, I begin by training and evaluating a logistic regression model with cross validation. I assess the model's accuracy using the true positive rate and false positive rate, as a low false positive rate is essential in order to maximize profit (and the true positive rate helps us distinguish our model from one which makes unsophisticated predictions).

Once an initial model has been created, I look at ways to deal with its obvious shortcomings. Primarily, the flaw in the model is that it does not deal well with the fact that most of the outcomes for the training set are positive. That is, in most cases, people pay back there loans. The model, therefore, can achieve "good" results by simply predicting repayment in all cases. To address this, I alter the logistic regression model to penalize misclassifications of negative results more strongly.

Finally, I try using a random forest classifier to make predictions. While this model was not optimized, the initial results were surprisingly poor. For a random forest classifier model which penalized negative results more strongly, the true positive rate and false positive rate were close to 1 - almost an indistinguishable result from a model which simply predicts repayment in all cases.
