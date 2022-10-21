# CharityML-Potential-Donor-classfication-based-on-income-data

![donor identification](https://github.com/SohamBera16/CharityML-Potential-Donor-classfication-based-on-income-data/blob/main/Charity-Image.png)

## Steps followed for this project:

### 1) Business Objective
In this project, several supervised machine learning algorithms have been implemented to accurately model individuals' income using data collected from the 1994 U.S. Census. Then, the best candidate algorithm out of the three tested algorithms from preliminary results have been chosen and further optimized to best model the data. The goal of this implementation is to construct a model that accurately predicts whether an individual makes more than $50,000. This sort of task can arise in a non-profit setting, where organizations survive on donations. Understanding an individual's income can help a non-profit better understand how large of a donation to request, or whether or not they should reach out to begin with.

### 2) Data collection
The dataset for this project originates from the UCI Machine Learning Repository. The datset was donated by Ron Kohavi and Barry Becker, after being published in the article "Scaling Up the Accuracy of Naive-Bayes Classifiers: A Decision-Tree Hybrid". You can find the article by Ron Kohavi online. The data we investigate here consists of small changes to the original dataset, such as removing the 'fnlwgt' feature and records with missing or ill-formatted entries.

### 3) Data exploration and investigating the data
Data understanding is gained for the use case by calculating factors like - Total number of people in the sample, number of people who earns or does not earn more than $50000, percentage of people in the sample with income greater than $50000. The featureset was also explored to gain some knowledge about the different factors that affect the income of a person for our sample.

### 4) Data preparation/preprocessing 
Checking for skewed features and performing logarithmic transformation to significantly reduce the range of values caused by outliers. 

![skewed distributions](https://github.com/SohamBera16/CharityML-Potential-Donor-classfication-based-on-income-data/blob/main/skewed%20distributions.png)

[However, Care must be taken when applying this transformation: As the logarithm of 0 is undefined, the values must be translated by a small amount above 0 to apply the logarithm successfully.]

![log transformed distributions](https://github.com/SohamBera16/CharityML-Potential-Donor-classfication-based-on-income-data/blob/main/log%20transformed%20dist.png)

 Normalization of the numerical features so that each feature is treated equally when applying supervised learners.
 
 In addition, One-hot encoding of categorical variables has been performed. As typically, learning algorithms expect input to be numeric, which requires that non-numeric features (called categorical variables) be converted.

### 5) Creation of a baseline "naive predictor" model to define what success means for this project
Based on the data exploration step, we create a naive predictor model which predicts that a person earns less than $50000 in all the cases as the data is skewed towards the class 0 (people earning less than $50K) so that we can compare the results of this naive predictor with the improved predictor for determining if machine learning is successful in providing better results than mere chance. 

### 6) Choosing the right metrics for model evaluation
As we have inherent data imbalance in the sample as the number of people who earn less than or equal to $50000 is much more than the ones who earn more than that benchmark. Hence, accuracy is not going to be an appropriate metric to evaluate our model prediction performance. Hence, to take into account the aspects of both precision and recall of our model, we use the F-beta score metric for model evaluation. 

### 7) Selection of a subset of appropriate models for the  problem 
Different candidate models were tested on a subset of the available dataset to choose the best model out of 3 candidate algorithms - Random Forest classifier, Support Vector Classifier, and Logistic Regression on the basis of training time as well as the achieved F1 score on the test dataset. 

![model selection](https://github.com/SohamBera16/CharityML-Potential-Donor-classfication-based-on-income-data/blob/main/performance%20comparison.png)

### 8) Initial evaluation of the chosen models and choosing the best model
depending on various metrics e.g. F score on the testing when 100% of the training data is used, prediction/training time, and the algorithm's suitability for the data.

### 9) Model tuning using Grid Search algorithm
Next, the chosen model's hyperparameters were tuned using the Grid search algorithm to find out the best set of hyperparameter values that would best fit the model into the chosen dataset. 

### 10) Final Model evaluation
#### 1) the optimized model's accuracy and F-score on the testing data are respectively 0.8420 and 0.6842. 2) The scores are slightly better than the results of the unoptimized model. 3) In comparison with the naive predictor's performance, which is Accuracy score: 0.2478, F-score: 0.2917, the optimized model has far outperformed the naive model.

### 11) Extracting Important features and corresponding Feature relevance observation
We choose a scikit-learn classifier (e.g., adaboost, random forests) that has a feature_importances_ attribute, which is a function that ranks the importance of features according to the chosen classifier. We fit this classifier to training set and use this attribute to determine the top 5 most important features for the census dataset.

![most predictive features](https://github.com/SohamBera16/CharityML-Potential-Donor-classfication-based-on-income-data/blob/main/most%20predictive%20features.png)

### 12) Feature selection and Dimensionality reduction
An attempt to reduce the feature space and simplify the information required for the model to learn was made according to the selected features. Then, the optimized logistic regression model was trained on the same training set with only the top five important features.

### 13) Effects of selecting certain features on the final model
The final model accuracy score with the important features sees a dip of approximately 4% in terms of accuracy score. But the more important factor for our imbalanced dataset problem, F-score, sees a huge drop of around 10% when we reduce the feature space.

#### Conclusion: 
Even if training time was an important factor, the prediction performance should not be compromised so much by using the reduced dataset as it might completely fail the goal of prediction (as can be seen from the downfall in F-score) using machine learning technology and bring us closer to the prediction probability of random chance! Moreover, the training time difference between the two is also not very high so as to slow down the decision making process. We can always send the emails to potential donors after a few days rather than sending a huge number of mails to non-donors causing us a huge


