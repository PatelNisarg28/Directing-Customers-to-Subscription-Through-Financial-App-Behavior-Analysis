# Financial App Behavior Analysis: Directing Customers to Subscription

## Overview

This project analyzes user behavior within a financial technology (Fin-Tech) mobile app that offers banking services like loans and savings. The app has two versions: Free and Premium. The free version includes basic features, while the premium version provides advanced capabilities for a fee. To boost sales of the premium version, the company offers customers 24-hour access to premium features to collect behavioral data.

The main objective is to predict which users are likely to buy the premium subscription. The goal is to minimize advertisement costs by targeting only the users who are interested but might not be able to afford the premium features, while avoiding offering discounts to users who would buy it anyway. Machine learning models are used to find insights from the collected customer behavior data and guide the company’s targeted marketing strategies.

## Problem Statement

The company aims to sell the premium version with minimal advertising cost but doesn't know how to identify potential customers. By analyzing user behavior, the machine learning model helps the company predict:

Which users will likely purchase the premium version without any incentive.
Which users are interested but need an offer to convert to premium.
This allows the company to strategically offer discounts to specific users, thereby maximizing profits without unnecessarily offering promotions to customers who would buy the product anyway.

## Dataset

The dataset comprises 50,000 records with 12 features, detailing user interactions within a financial app, such as login times, visited screens, and whether the user enrolled in premium features.

### Key Features:
- **user**: Unique identifier for each user.
- **first_open**: Date and time when the user first accessed the app.
- **dayofweek**: Day on which the user logged into the app.
- **hour**: Hour of the day when the user accessed the app.
- **age**: Age of the user.
- **screen_list**: List of screens accessed by the user.
- **minigame**: Whether the user engaged with mini-games within the app.
- **used_premium_feature**: Indicates if the user used any premium feature.
- **enrolled**: Target variable, whether the user subscribed to the premium feature.
- **enrolled_date**: Date when the user enrolled in the premium feature.
- **liked**: Whether the user liked the app feature.
- **dayofweek**: Day when the user interacted with the app.

### Missing Data:
The dataset contains some missing values, especially in the `enrolled_date` field, which need to be handled during preprocessing.

## Data Preprocessing

1. **Missing Values**: Missing values in critical columns such as `enrolled_date` were identified.
2. **Feature Engineering**: 
   - Extracted meaningful information from the `screen_list` column.
   - Encoded categorical features like `dayofweek` and `hour`.
   - Created new features from existing ones to improve prediction accuracy.
   
## Modeling Approach

We used the following techniques to predict whether a user will subscribe to premium features:

1. **Data Normalization**: StandardScaler was used to normalize continuous variables.
2. **Dimensionality Reduction**: PCA (Principal Component Analysis) was applied to reduce feature dimensions and avoid overfitting.
3. **Machine Learning Models**:
   - **Logistic Regression**
   - **Decision Trees**
   - **Random Forest**
   - **Support Vector Machine**
   - **XGBoost**

### Evaluation

Models were evaluated using the following metrics:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**

The XGBoost model, with 78.83% accuracy, outperformed other models like SVC, Random Forest, etc... Behavioral features like screen navigation and time of app usage were key predictors of user intent.

## Results and Insights

- **Key Insight**: Users who accessed specific screens (such as product reviews and reward-related screens) and those who played mini-games were more likely to subscribe to premium features.
- **Feature Importance**: The most influential features included the `screen_list`, `used_premium_feature`, and time-related variables like `hour` and `dayofweek`.

## Business Strategy Insights
- **Targeted Offers**: The company should offer discounts only to users who show interest in the premium features but are unlikely to purchase without an offer. This avoids wasting marketing resources on users who would purchase the product without a promotion.
- **Behavioral Patterns**: Users who navigate specific screens and use premium features are more likely to convert to premium subscriptions, offering valuable insights into user engagement.

## Conclusion

This project provides actionable insights into customer behavior, enabling the company to implement targeted marketing strategies. The machine learning models help reduce unnecessary advertising costs while increasing the number of premium subscriptions by focusing on users who are most likely to convert with an offer.
