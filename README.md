# AB_NYC_2019
Source : https://www.kaggle.com/dgomonov/new-york-city-airbnb-open-data

Airbnb has seen massive growth to become one of the most popular accommodation platforms for travelers. It has transformed the hospitality industry and the way people travel. New York City, as one of the biggest cities in the world, has a very high amount of Airbnb traffic. This project thus focuses on Airbnb in New York City and has two main purposes: 
1. To analyze meaningful Airbnb trends in New York City via data visualizations
2. To get intuitions and find correlations by statistical methods

Part 1: Analysis of meaningful Airbnb trends in New York City 

In this section, we experimented with different data visualization techniques to derive the most meaningful analysis of Airbnb trends in New York City. Our visualization techniques include bar charts, scatter plots, and line charts. 

a. Bar charts 
We first began with bar charts as they are a simple yet effective form of data visualization. With the bar charts, we visualize average price by borough, number of listings by borough and average availability out of 365 days a year by borough. Expectedly, we found that Manhattan is the most expensive borough with an average of $190 per night and with the most number of listings with over 20,000. Brooklyn stands second followed by Queens. Given the distance from the city and inconvenience of public transportation, Staten Island has very few listings and most highest average availability. Lambda was used for data wrangling. We carried out the same exercise for room types. Entire apartments are the most expensive, require the highest number of minimum nights and have the most listings. 

b. Scatter plots 
Secondly, we tried to observe and show relationships between price and other numeric variables by generating scatter plots for each borough. 
Numeric Values on x-axis: availability out of 365 days a year, reviews per month, total number of reviews, calculated host listings count and minimum nights
Numeric Values on y-axis: Price
Not all scatter plots indicate a clear trend. Out of the five numeric variables, we derived the most 2 meaningful trends which are reviews per month vs price, and minimum nights vs price. 
In general, price tends to decrease for longer stays but 30-day stay appears to be an exception.
Reviews per month tend to increase for cheaper stay options. Although the number of reviews vs price plot created a similar output to what the reviews per month and price plot created, we didn’t find this plot consistent as it includes the time factor of the number of reviews variable. We couldn’t identify any kind of trend pattern between the availability vs price and calculated host listings count vs price. 

c. Line charts
We also want to analyze the data through prices and minimum nights by neighborhood. Given the large number of neighborhoods, we derived a tool for users to input the neighborhood they want to examine. The top 10 highest prices and the 10 lowest prices would appear, together with the line graph of all the prices in that neighborhood (y-axis) vs the minimum nights (x-axis). 
This tool will allow users to view how high or low the prices can be fluctuating for a specific neighborhood and also with the help of the line graph the users can visualize the highest and lowest prices by minimum nights. This enables a wider range for users in terms of getting an idea while booking a room if they are planning for certain minimum nights and are able to manage the budget for the accommodation. 

Part 2: To get intuitions and find correlations by statistical methods 

In this section, we aim to find the best statistical model to predict the price of Airbnb in New York City using different statistical methods. The methods that we experimented with are: linear regression, regularization, logistic regression and random forest. For linear regression we gregress price on minimum nights, reviews per month, listing count, availability and boroughs.  5 boroughs are converted to a dummy variable first then we fit a regression line. Although some coefficients are significant but Adjusted R squared is only 0.038. Only 3.8% of variability in price can be explained by above mentioned predictors.
Scikit-learn library was used to split the data into train and test to use regularization methods by Lasso and Ridge regression. They did not improve the model.
Classification:
We tried to predict if a property is a house/apt based on Longitude, Latitude, minimum nights, listing count and availability. We applied logistic regression. The accuracy score and the confusion matrix were not promising

Random forest could predict the type of the property better than logistic regression but still not promising:
 
In the end, we applied Random Forest classifier to see if we can categorize a private room in Manhattan to low price and high price (compared to average price of a private room in Manhattan). We used 70% of data for the train set and 30% for the test set. The model could predict the class of the test set 72% of time correctly:

