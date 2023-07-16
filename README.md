# online_shopping_intent

## Introduction
Online shopping and e-commerce are fast becoming the predominant medium for the exchange of goods and services. It is in the best interest of digital marketers, business owners, and analysts alike to understand factors that contribute to an online purchase being made. The goal of this analysis is to predict revenue based on various purchase intent factors measured by the activity of a user on an e-commerce website. The dataset contains information about a binary dependent variable, Revenue, along with variables such as the number of pages visited per category and other Google Analytics metrics. We used a variety of modelling methods to predict revenue as well as infer the relationship between revenue and predictor variables.

## Data Description
The data we used for this analysis was provided through University of California, Irvine (UCI) Machine Learning Repository, but per the website, the data was originally taken from C.Okan Sakar and Yomi Kastro, faculty of Bahcesehir University. The data set provides information about purchasing intent of online shoppers. Independent variables in this data provide a spectrum of information, ranging from Google Analytics rate data to region, month, special occasions, and time spent on viewing similar products. There are 12,330 rows and 18 columns, with no missing value. The targeted variable contains 10,422 records of instances where a purchase was not made and only 1,908 instances where a product was purchased. Therefore, this dataset is highly imbalanced. 

## Methodology
* Logistics regression
  * logistic regression is often the top pick for benchmark models to measure model performance because it is the simplest machine learning algorithm and easy to implement. The predicted parameters give       inference about the importance of each feature, so it can easily use the model to find out the relationship between each predictor and the dependent variable.
    
* Discriminant analysis
  * Linear discriminant analysis (LDA) is used when a linear boundary is required between classifiers, and it follows the Bayes rule under
    the assumption of normality for the distribution of observations in each response class with class-specific mean and common variance.
  * Unlike LDA, quadratic discriminant analysis (QDA) is used to find a non-linear boundary between classifiers.
 

## Result 
* Logistics regression
  * By performing 10-fold cross-validation for the full model and reduce model, the AUC values suggested that our model has been improved by variable selection stepwise in both directions by measuring         AIC. In addition, the test for a subset of coefficients supports that Administrative_Duration, Informational_Duration, Region are not significant in making predictions.
  * The result of the Goodness of fit test suggested that the reduced model is not an adequate fit for the dataset. Goodness of fit does not guarantee good predictions and it does not mean that our   
    independent variables are not good predictors of our dependent variable.
  * PageValue, exitRate, productRelated_Duration, month, and traffic type are remaining to be most important variables in classifying Revenue, even though we performed variable selection.
    
* Discriminant analysis
  * Found these variables have significant difference in group mean: Administrative_Duration, Informational_Duration, ProductRelated, ProductRelated_Duration, and PageValues. Fitted a model with all         these variables above, model accuracy has been improved.
  * Compared with QDA, a linear classifier is more suitable for our dataset since it has higher model accuracy.
  * From our model output, we can see the separation between these two groups is quite close with lots of overlapping.
 
## Findings
* Logistics regression
  * Decision boundary helps to differentiate probability into positive class and negative class. Our final model has the highest accuracy when the misclassification threshold reaches 0.75 and then it        starts to decrease. Even though we have a more accurate model, we resulted in more false positive cases, which could result in a loss of revenue.
  * People are more likely to make purchases in May, March, and December from the reduced model.
    
* Discriminant analysis
  * For customers who made purchases, the amount of time spent on administrative page (eg. login, entering shipping/billing info), specific product page and product category page (looking for similar        products) are significantly higher than customers who did not make purchases.
  * Customers who did not make purchases have a higher exit rate than customers who made purchases.
  * Customers who did not make purchases have a higher bounce rate than customers who made purchases. (bounce rate is the percentage of visitors who enter the website through that page and exit              without triggering any additional task)
  * Surprisingly, with those variables having significant differences in group mean, they don't have large coefficient values.















  
