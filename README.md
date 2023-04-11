# Predicting-Customer-Satisfaction-in-Airline-Industry

## Business Understanding

Pandemic was tough on the Airline Industry. With increase in restrictions, cut throat pricing, operational failures and decreasing level of amenities, this industry is struggling to retain customers and keep their satisfaction level up. This project is for stakeholders who might be interested in knowing what matters the most to the customers through prediction of customer satisfaction based on survey data. 

## Data Understanding

The dataset contains 25 features (coulmns) and 129882 customer observations (rows). The target variable here was customer satisfaction (binary variable: Satisfied/Neutral or Unsatisfied)

Features of dataset:
1. Demographics: gender, age, type of travel, customer type
2. Flight Data: class, distance, departure delay, arrival delay
3. Flight Services (Scale 0-5): comfort, cleanliness, online boarding, etc.

## EDA 

Following was found from the EDA results:
1. Distribution of satisfaction over population based on the gender was very similar

![Screenshot 2023-04-10 204811](https://user-images.githubusercontent.com/129342521/231026869-18c9dd75-48cf-4efd-9f0d-fcb3a9ce053c.png)

2. Younger population was largely found to be neutral or disappointed. Customers in the age range from 35 to 55 were generally more satisfied than dissatisfied. 

![Screenshot 2023-04-10 204959](https://user-images.githubusercontent.com/129342521/231027071-96fdff8f-943a-4c0d-b1d3-7ce1ba444801.png)

3. During journeys with shorter distances, customers were more disappointed/neutral than satisfied

![Screenshot 2022-10-16 160239](https://user-images.githubusercontent.com/129342521/231027198-79f8892c-eea7-48df-928d-20bcd3124890.png)

4. Customers traveling in business class appear to be more satisfied than the customers traveling in economy or economy plus class. 

![Screenshot 2023-04-10 205234](https://user-images.githubusercontent.com/129342521/231027337-f887c639-181f-4d86-8aff-cee8e78b5112.png)

5. Also used PCA analysis to find unique relations between different factors. Found that low satisfaction associated with low in-flight entertainment, seat comfort, online boarding. 

![Screenshot 2023-04-10 205417](https://user-images.githubusercontent.com/129342521/231027532-a20d897f-bb0d-429d-8586-deffb06e7dc1.png)

## Data Preparation

1. Removed missing values: There were 310 missing values in "Arrival.Delay.in.Minutes". Replaced NA's with its median = 0 to normalize it. Removed column X and Id
2. Dummy Variables: For target variable "Neutral or dissatisfied” to be "0", “satisfied” to be "1". Segregated Gender, Customer.Type, Type.of.Travel, Class(into 3 variables)
3. Outliers: The variables with outliers are departure delay, arrival delay, flight distance, and rating on check-in service. However, all of these variables cannot be modified because even outliers present essential meanings in real cases

![Screenshot 2023-04-10 205956](https://user-images.githubusercontent.com/129342521/231028196-5a66a9bb-6d11-45ac-8ad9-47de1d4d324b.png)

4. Correlation: Checked correlation between variables with outliers. High correlation between departure delay and arrival delay. Dropped Arrival.Delay.in.Minutes to avoid multicollinearity.

![Screenshot 2023-04-10 210128](https://user-images.githubusercontent.com/129342521/231028359-da6035dd-ae7d-427e-8ca5-da9b595e8eb0.png)

## Modelling

Implemented the following models and their respective Accuracy (OOC testing)

1. Simple Logistic Regression: 0.8714968
2. Logistic Regression with Interactions: 0.9327841
3. Logistic Regression after Lasso feature selection: 0.51
4. Classification Tree: 0.8845
5. Random Forest: 0.962963
6. Neural Networks: 0.9497 

## Conclusion and Recommendations

Looking the results, for improved customer satisfaction in short term airlines should focus on the following 2 features:

1. In-Flight Entertainment: Predictors of Customer Satisfaction : In-flight entertainment, in-flight service, and seat comfort. The probability of satisfaction goes up by 72%, 57%, and 55% for every point increase in satisfaction. Further study on what customers value for the in-flight entertainment.

2. In-Flight Wi-Fi and Online Boarding: Random forest and logistical regression with lasso feature selection. Interaction increases customer satisfaction by 56% for every scaled point increase. Improve on online services and in-flight Wi-Fi to improve customer satisfaction.

Data Source : https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction
This project was done in team as part of my data science coursework during grad school.
