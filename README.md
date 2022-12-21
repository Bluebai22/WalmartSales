# WalmartSales
This is the data analysis projects using Machine Learning models, trying to figure out the potential factors impacted on Walmart weekly sales.

# Data Source 
We used Walmart Sales date set downloaded from Kaggle. The dataset includes historical data for 45 Walmart stores and each store contains a number of departments.
The data file comes with four different datasets, which are table including all the features, table including the target variables, and table including store' infomation.

# Data Preparation
After glancing at the row data. We right join features table and target table on variable Date. Then left join the new table with table store on variable Store. Then, we changd the type of store and department from number into category.
To furthur clean the dataset, we removed the missing value and random selected 10% date of year 2012 to avoid running slow and overload problem.

# Data Visulization
To better understand the data structure, we used different plot to visualize the features and target variable, such as line chart, bar chart and scatter plot. After looking through the heatmap, it seems that MarkDown4 is highly correlated with MarkDown1. To avoid collinearity issue, we will drop MarkDown4.

![plot](https://github.com/Bluebai22/MoviePreference/blob/main/Github/ml-linechart.png)

![plot](https://github.com/Bluebai22/MoviePreference/blob/main/Github/ml-barchart.png)

![plot](https://github.com/Bluebai22/MoviePreference/blob/main/Github/ml-scatter%20plot.png)

![plot](https://github.com/Bluebai22/MoviePreference/blob/main/Github/ml-heatmap.png)

# Target Variable and Features
After looking through the relationshop between features and target variable Weekly Sales, we decide to use following variables as feature for our model.

Features:
Temperature: average temperature in the region
Unemployment: the unemployment rate
MarkDown1,2,3: anonymized data related to promotional markdowns that Walmart is running. MarkDown data is only available after Nov 2011, and is not available for all stores all the time. Any missing value is marked with an NA.
IsHoliday: whether the week is a special holiday week
Type: type of store
Size: size of store
Dept: department of store
Store: the walmart store

# Modeling
We tried 6 different model, ranging from most basic Linear Regression, to ensamble model Random Forest. During the process, we used cross validation and Grid Search to find the best parameters. Following is the rank of the test score of 6 models.

1) Random Forest: Train score: 0.95; Test score:0.65
2) Decision Tree: Train score: 0.81; Test score:0.47
3) Kernel Ridge Regression: Train score: 0.06
4) Ridge Regression:Train score: 0.14
5) Linear Regression: Train score: 0.094; Test score:0.049
6) SVMs(Support vector machines): Train score: -0.38

# Best Model - Random Forest

![plot](https://github.com/Bluebai22/MoviePreference/blob/main/Github/randomforest1.png)
![plot](https://github.com/Bluebai22/MoviePreference/blob/main/Github/randomforest2.png)


# Conclusion
For Walmart data, SVM regression gives the worst performance. It may be beacuse as we see in the data visualizations, most of the features are not showing any visible trends. Since most of the data points are cluttered near a range of low weekly sales, it may be difficult for SVM to find a best fit line that contains the maximum number of datapoints. Similarly, linear and kernel ridge shows the second worse performance since we did not add any non-linear features. Kernel ridge captures some non-linear features, but we might need to add interaction or cluster variables. Since decision trees and random forest captures non linear features as well as take care of the interaction within the features and clusters, their performance is a big improvement from other models. However, it should be note that even though the performance is better, they also seem to have more overfitting issues than other models.




