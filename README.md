# gardenia_project
This repository is created for the final project submitted for Exploratory Data Analytics course.

Basically this project is chosen from www.analyticsvidhya.com. A Competition held in website during sep 24 to oct 02 2016 with name “Ultimate student hunt”. We take that as our project for subject. The project is aimed to develop a prediction for footfall in park present in Gardenia Country. So, data is given for various park of gardenia country for the period of 1990 to 2005. There are total 18 parameters in data.
Competition page is https://datahack.analyticsvidhya.com/contest/the-ultimate-student-hunt/.

Problem Statement: -
Welcome to Gardenia - A country which believes in creating a harmony between technology and natural resources. Over the years, Gardenia has come up with ways to utilise natural resources effectively and they have enabled this with use of cutting edge technology. 
The country takes pride in the way it has maintained its natural resources and Gardens. Now, the government of Gardenia wants to use data science to understand the health habits of their citizens. So, they started to capture several variables from various parks in the country.
They now have this data over a long period of time and are looking for experts like yourself to look at the data and tell, if you can predict how many people will come to a park on a particular day, given the environmental information.
Go, help the mayor of Gardenia! He has high hopes from Analytics Vidhya community! All the best!



Data Definition
Variable ->	  Definition
ID	->  Unique ID
Park_ID ->	Unique ID for Parks
Date ->	Calendar Date
Direction_Of_Wind ->	Direction of winds in degrees
Average_Breeze_Speed ->	Daily average Breeze speed
Max_Breeze_Speed ->	Daily maximum Breeze speed
Min_Breeze_Speed ->	Daily minimum Breeze speed
Var1	A continuous -> feature
Average_Atmospheric_Pressure ->	Daily average atmospheric pressure
Max_Atmospheric_Pressure ->	Daily maximum atmospheric pressure
Min_Atmospheric_Pressure ->	Daily minimum atmospheric pressure
Min_Ambient_Pollution	Daily -> minimum Ambient pollution
Max_Ambient_Pollution	Daily -> maximum Ambient pollution
Average_Moisture_In_Park ->	Daily average moisture
Max_Moisture_In_Park ->	Daily maximum moisture
Min_Moisture_In_Park ->	Daily minimum moisture
Location_Type ->	Location Type (1/2/3/4)
Footfall ->	Target Variable: Daily Footfall

How we solve the problem?
	By seeing the data & problem we can say that it is a problem of regression. Regression is a supervised machine learning technique which will tell the relation between one dependent variable & one or more independent variable. It is useful for predictive analysis purpose.

	So here we are using XGBoost regressor to do the regression. XGBoost is an advanced tree based gradient boosting method.

	 In code first we are doing data cleansing and removing of target variable to train the model.

	And as we are using regression for solving the problem we converted all categorical variable to numerical data by convert them into matrix.

	As the data is a time series data we parse the date and add some data related to date in the actual data like proper day, day of week, day of month, day of year and with this we also add the rolling mean, standard deviation, min, max for each column to data.

	After doing cleansing & pre-processing we are generating the aggregate data to be used to pre-processed data.

	And at last we are using ensemble of xgboost regressor to predict the footfall for data with minimum RMSE value will achieve.



