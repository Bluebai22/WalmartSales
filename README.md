# WalmartSales
This is the data analysis projects using Machine Learning models, trying to figure out the potential factors impacted on Walmart weekly sales.

# Data Source 
We used Walmart Sales date set downloaded from Kaggle. The dataset includes historical data for 45 Walmart stores and each store contains a number of departments.
The data file comes with four different datasets, which are table including all the features, table including the target variables, and table including store' infomation.

# Data Preparation
After glancing at the row data. We right join features table and target table on variable Date. Then left join the new table with table store on variable Store.
To furthur clean the dataset, we removed the missing value and random selected 10% date of year 2012 to avoid running slow and overload problem.

# Data Visulization
To better understand the data structure, we used different plot to visualize the features and target variable, such as line chart, bar chart and scatter plot.

![plot] (https://github.com/Bluebai22/MoviePreference/blob/main/Github/ml-linechart.png)

![plot] (https://github.com/Bluebai22/MoviePreference/blob/main/Github/ml-barchart.png)

![plot] (https://github.com/Bluebai22/MoviePreference/blob/main/Github/ml-scatter%plot.png)
