# Online Delivery Customer Churn Prediction

# Definintion of Churn Prediction
Churn prediction means detecting which customers are likely to leave a service or to cancel a subscription to a service. It is a critical prediction for many businesses because acquiring new clients often costs more than retaining existing ones.
Churn prediction modelling techniques attempt to understand the precise customer behaviours and attributes that signal the risk and timing of customers leaving. It’s not a walk-in-the-park task so I mention just four points to consider.

# Motivation
It is a critical prediction for many businesses because acquiring new clients often costs more than retaining existing ones.
In order to grow your company, it is essential to invest in acquiring new clients. Every time a client leaves, it represents a significant investment lost. Both time and effort need to be channelled into replacing them. Being able to predict when a client is likely to leave, and offer them incentives to stay, can offer huge savings to a business.

As a result, understanding what keeps customers engaged is extremely valuable knowledge, as it can help you to develop your retention strategies, and to roll out operational practices aimed at keeping customers from walking out the door.

Predicting churn is a fact of life for any subscription business, and even slight fluctuations in churn can have a significant impact on your bottom line. We need to know: “Is this customer going to leave us within X months?” Yes or No? It is a binary classification task.


# Objective
The main objective of this project is to 
* Perform extensive Exploratory Data Analysis(EDA) on the online delivery Dataset. 
* Tranform the data to an appropriate form
* Build a few Machine Learning models and perform performance metrics.
* Compare the models and deploy the best machine learning model

# Dataset
There has been a rise in the demand of online delivery in the metropolitan cities such as Bangalore in India. The question about why this increase in the demand has always been a lingering question. So a survey is conducted and the data is presented.

The dataset has nearly 55 features based on the following titles and 388 data points.
Demographics of consumers
* Overall/general purchase decision
* Time of delivery influencing the purchase decision
* Rating of Restaurant influencing the purchase decision

# Steps Involved

## Data Analysis

* **Pandas Profiling**

* **Geospatial Data Analysis**

* **Categorical Grouping**

* **Visualization of Continuous variables**

## Feature Engineering:

This is the most important step for any data science based application. We have to select the relevant features.

Feature engineering refers to a process of selecting and transforming variables when creating a predictive model using machine learning or statistical modeling (such as deep learning, decision trees, or regression). The process involves a combination of data analysis, applying rules of thumb, and judgement. It is sometimes referred to as pre-processing, although that term can have a more general meaning.

* Dropping unnecessary features: 'Medium (P2)', 'Meal(P2)', 'Perference(P2)', 'latitude', 'longitude', 'Reviews', 'Pin code'
* Stripping and renaming feature names
* Converting categorical features to numerical features manually
* Converting categorical features to numerical features using cat.codes

### One Hot Encoding
This procedure is done for XGBoost, where the following categorical features are categorically coded using OneHotEncoder:

'Gender', 'Marital_Status', 'Occupation', 'Monthly_Income', 'Educational_Qualifications', 'Family_size', 'Time_saving', 'Good_Quantity','Meal', 'Preference', 'Medium', 'Ease_and_convenient', 'More_restaurant_choices', 'Easy_Payment_option', 'More_Offers_and_Discount', 'Good_Food_quality', 'Good_Tracking_system', 'Self_Cooking', 'Health_Concern', 'Late_Delivery', 'Poor_Hygiene', 'Bad_past_experience', 'Unavailability', 'Unaffordable', 'Long_delivery_time', 'Delay_of_delivery_person_getting_assigned', 'Delay_of_delivery_person_picking_up_food', 'Wrong_order_delivered', 'Missing_item', 'Order_placed_by_mistake', 'Influence_of_time', 'Order_Time', 'Maximum_wait_time', 'Residence_in_busy_location', 'Google_Maps_Accuracy', 'Good_Road_Condition', 'Low_quantity_low_time',  'Delivery_person_ability', 'Influence_of_rating', 'Less_Delivery_time',  'High_Quality_of_package', 'Number_of_calls', 'Politeness', 'Freshness_', 'Temperature', 'Good_Taste_' 
       
## Feature Scaling
XGBoost is not sensitive to monotonic transformations of its features for the same reason that decision trees and random forests are not: the model only needs to pick "cut points" on features to split a node. Splits are not sensitive to monotonic transformations: defining a split on one scale has a corresponding split on the transformed scale.

## Train-Test Split
Splitting the transformed dataset randomly into 70% training and 30% testing dataset.

## Models:
A total of 7 models are built namely: 
* XGBoost: 
  * GridSearchCV 
  * Basic XGBoost
* Support Vector Machine: 
  * Randomized Search
  * Grid Search
  * Basic Linear SVM
  * Basic Sigmoid SVM
  * Basic RBF SVM
* K Nearest Neighbor:
  * Grid Search KNN
  * Basic KNN
* Random Forest Classifier:
  * Grid Search
  * Random Search
  * Basic Random Forest
* Decision Tree:
  * Gini Decision Tree
  * Entropy Decision Tree
* Logistic Regression:
  * Grid Search
  * Basic Logistic Regression
* Naive Bayes:
  * Multinomial Naive Bayes
  * Gaussian Naive Bayes
## Comparison Between models:

### Definition:
* **Accuracy**: represents how well classifier can classify true positives and true negatives
* **Specificity** or *True Negative Rate* represents the ratio of true negatives predicted wrt to the total actual negatives.
* **F1-Score** represents the Harmonic mean of Precision and Recall.
* **Receiver Operator Characteristic (ROC) curve**: Evaluation metric, probablity curve that plots TPR and FPR for various threshold values.
* **Area Under Curve (AUC)**: Summary of ROC curve and measures the ability of classifier to distinguish between positive and negative classes

![Screenshot (47)](https://user-images.githubusercontent.com/109594714/185834905-28b34274-261a-4912-bd40-7329e530a50a.png)
![Screenshot (48)](https://user-images.githubusercontent.com/109594714/185835148-41a95634-1d5d-4708-9c1e-8e24d3164932.png)

Higher the AUC, better the performance of the model

**Best Performance according to various metrics:**

* AUC_PR Scoree: 100% (XGBoost - Grid Search)
* AUC_ROC Score: 98% (XGBoost - Grid Search)
* F1 Score: 96% (XGBoost - Grid Search)
* Accuracy: 93.81% (XGBoost - Grid Search)



