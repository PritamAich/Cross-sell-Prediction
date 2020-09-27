# <ins>Cross-sell Prediction</ins>

## Project Overview:

This is a Competition held by Analytics Vidhya. 

Competition name : [Janatahack: Cross-sell Prediction](https://datahack.analyticsvidhya.com/contest/janatahack-cross-sell-prediction/#About)

#### Intro

Cross-selling identifies products or services that satisfy additional, complementary needs that are unfulfilled by the original product that a customer possesses. As an example, a mouse could be cross-sold to a customer purchasing a keyboard. Oftentimes, cross-selling points users to products they would have purchased anyways; by showing them at the right time, a store ensures they make the sale.

Cross-selling is prevalent in various domains and industries including banks. For example, credit cards are cross-sold to people registering a savings account. In ecommerce, cross-selling is often utilized on product pages, during the checkout process, and in lifecycle campaigns. It is a highly-effective tactic for generating repeat purchases, demonstrating the breadth of a catalog to customers. Cross-selling can alert users to products they didn't previously know you offered, further earning their confidence as the best retailer to satisfy a particular need.

<img src = "images\cross_sell.png" >

The dataset used in this project can be found at the bottom of [this page](https://datahack.analyticsvidhya.com/contest/janatahack-cross-sell-prediction/#ProblemStatement)

#### Our Goal

Building a model to predict whether a customer would be interested in Vehicle Insurance. 
It is extremely helpful for the company because it can then accordingly plan its communication strategy to reach out to those customers and optimise its business model and revenue.

### Outcome: 

Achieved 86.28% Accuracy in predicting the response of customers for the vehicle insurance, in the Private Leaderborard of the competition.

## Resources:

**Python version :** 3.7
**Packages Used:** pandas, numpy, matplotlib, seaborn, sklearn, tensorflow.

## Project Architecture:

- **Dataset Description**

<img src = "images\dataset.png" >

- **Exploratory Data Analysis**

    - Visualization of class imbalancement
    - Plotting graphs of features to find any meaningful insight

- **Data Preprocessing**

    - Dropping null values, handling categorical data
    - Scaling data (Standardization)

- **Model Building**

    - Trying out four different models.
    - Validating model performance on Validation data

- **Testing**

    - Generating test predictions
    - Creating submission file for final evaluation in the contest.



### 1. Exploratory Data Analysis(EDA):

a) At first, all the data is gathered. The training and test set were already in seperate csv files.

b) Gathered information on how imbalanced the dataset is.

<img src = "images\classes.png" >

c) Did some exploration on several other features and some noticable of them are listed below:

- Distribution of Age:

<img src = "images\age_dist.png" >

It can be deduced that most people who took insurance are aged between 20 and 40. This will help the marketting team to plan further actions on these customers to increase their revenue.

- Annual Premium  amount distribution:

<img src = "images\annual_dist.png" >

- Vehicle Damage:

<img src = "images\vehicle_damage.png" >

From this, it is clear that those customers who have a past damage record for their vehicles tend to take the vehicle insurance.

- Previous Insurance:

<img src = "images\customer_response.png" >

The customers who already have an insurance won't take anotheer insurance as it will only create a burden upon them.
This is a key insight for the amrketting team and it will save them time and resources by not targetting the customers with previous insurance record.


- Correlation of independent features with target feature(Response):
<img src = "images\corr_bar.png" >

Find more exploration of the dataset in this [notebook]()


### 2. Data Preprocessing:

a) Data preprocessing includes treatment of null values(though there wasn't any null value), handling categorical data.

b) Creating dummies of categorical data.

c) Since the dataset was highly imbalanced, used Stratified K-Folds cross-validator to split the dataset in equal ratio of the two classes.

d) Scaling of data is down using MinMaxScaler from sklearn package.


### 3. Model Building:

a) Four different Machine Learning models were used for this project.

- Random Forest
- XGBoost
- CatBoost
- Light GBM(LGBM)

Their respective validation scores compared below.

<img src = "images\models.png" >


b) The evaluation metric used is [Roc-Auc score](https://towardsdatascience.com/understanding-auc-roc-curve-68b2303cc9c5#:~:text=AUC%20%2D%20ROC%20curve%20is%20a,problem%20at%20various%20thresholds%20settings.&text=By%20analogy%2C%20Higher%20the%20AUC,is%20on%20the%20x%2Daxis.).

LGBM gave slightly better validation performance score than CatBoost.

c) There is also basic Neural network model that was applied in this dataset. It can be found [here]()

### 4. Testing:

a) Tested the model on test data and generated predictions.
b) Created a submission file with the generated predictions and submitted to the contest.

The model scored 85.80% accuracy in public leaderboard and 86.28% accuracy in the private leaderboard where the model was re-evaluated in the final evaluation/ test dataset.

**Ranked 107 out of 20674 participants.**
