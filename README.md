# CharityML-Potential-Donor-classfication-based-on-income-data

## Steps followed for this project:

### 1) Business Objective
In this project, several supervised machine learning algorithms have been implemented to accurately model individuals' income using data collected from the 1994 U.S. Census. Then, the best candidate algorithm out of the three tested algorithms from preliminary results have been chosen and further optimized to best model the data. The goal of this implementation is to construct a model that accurately predicts whether an individual makes more than $50,000. This sort of task can arise in a non-profit setting, where organizations survive on donations. Understanding an individual's income can help a non-profit better understand how large of a donation to request, or whether or not they should reach out to begin with.

### 2) Data collection
The dataset for this project originates from the UCI Machine Learning Repository. The datset was donated by Ron Kohavi and Barry Becker, after being published in the article "Scaling Up the Accuracy of Naive-Bayes Classifiers: A Decision-Tree Hybrid". You can find the article by Ron Kohavi online. The data we investigate here consists of small changes to the original dataset, such as removing the 'fnlwgt' feature and records with missing or ill-formatted entries.

### 3) Data exploration and investigating the data
Data understanding is gained for the use case by calculating factors like - Total number of people in the sample, number of people who earns or does not earn more than $50000, percentage of people in the sample with income greater than $50000. The featureset was also explored to gain some knowledge about the different factors that affect the income of a person for our sample.

### 4) Data preparation/preprocessing 
Checking for skewed features, performing logarithmic transformation to significantly reduce the range of values caused by outliers. [However, Care must be taken when applying this transformation: As the logarithm of 0 is undefined, the values must be translated by a small amount above 0 to apply the logarithm successfully.]

 Normalization of the numerical features so that each feature is treated equally when applying supervised learners.
 
 In addition, One-hot encoding of categorical variables has been performed. As typically, learning algorithms expect input to be numeric, which requires that non-numeric features (called categorical variables) be converted.

### 5) Creation of a baseline "naive predictor" model to define what success means for this project
Based on the data exploration step, we create a naive predictor model which predicts that a person earns less than $50000 

### 6) Choosing the right metrics for model evaluation
As we have inherent data imbalance in the sample as the number of people who earn less than or equal to $50000 is much more than the ones who earn more than that benchmark. Hence, accuracy is not going to be an appropriate metric to evaluate our model prediction performance. Hence, to take into account the aspects of both precision and recall of our model, we use the F-beta score metric for model evaluation. 

### 7) Selection of a subset of appropriate models for the  problem 

### 8) Initial evaluation of the chosen models and choosing the best model
depending on various metrics e.g. F score on the testing when 100% of the training data is used, prediction/training time, and the algorithm's suitability for the data.

### 9) Model tuning using Grid Search algorithm

### 10) Final Model evaluation

### 11) Extracting Important features and corresponding Feature relevance observation

### 12) Final important Feature selection and effects of selecting certain features on the final model


