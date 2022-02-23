# FormulaAI-WeatherPrediction


## [Exploratory Data Analysis:](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/WeatherFormulaAIEDA.ipynb)
### Data Preprocessing:

Whether it is AI or ML, the foundation is data and lots of it. Every business has this data in one form or the other but it has to be cleaned and prepared into a state that can be used by Machine Learning to learn from. Data sources for a business can be both proprietary as well as from open sources such as weather data, traffic data etc.
 Business owned data can be numeric(loan amount, customer retention rate), categorical(gender, color, property type), time stamped (how many products were purchased in a time range) or even free text (think emails, doctor’s notes)
For our current analysis the data has a total of 58 features, with 11 features with highest missing values, while 7 of them with single missing values that we are imputation later on.
The Next Steps is Statistical Analysis.

### Statistical Analysis:
Statistics is used in a variety of sectors in our day-to-day life for analyzing the right data.
Define your question, Collect the right data, Understand the data, Cleaning the data, Analyze the data and finally interpret the results for the questions.

	- Pearson correlation
	- Statistical Summary
  
 ### Feature Extraction:
Feature selection is to reduce the number of input variables when developing a predictive model. It is desirable to reduce the number of input variables to both reduce the computational cost of modeling and, in some cases, to improve the performance of the model. The feature importance (variable importance) describes which features are relevant. Random Forests are often used for feature selection in a data science workflow. The reason we used it here is because the tree-based strategies used by random forests naturally ranks by how well they improve the purity of the node. This means a decrease in impurity over all trees. 
So, There is 10 features/attributes whose importance is above the threshold.
We used the following 2 methods for Feature Extraction and got the same set of metrics as stated below:
1. KBest Method
2. Random Forest

These are the 10 selected features and their feature importance score.
Feature | Score
M_SESSION_UID  3.858013e+23
M_SESSION_LINK_IDENTIFIER  3.788487e+14
M_WEEKEND_LINK_IDENTIFIER  3.788487e+14
M_SEASON_LINK_IDENTIFIER  3.788487e+14
M_SESSION_DURATION  9.514273e+08
M_FRAME_IDENTIFIER  9.229148e+08
M_SESSION_TIME_LEFT  1.304397e+08
TIMESTAMP  1.027454e+08
M_TRACK_LENGTH  7.654119e+07
M_SESSION_TIME  4.096546e+07


## [Selection of Classifier based on AUTO ML results:]()
* Decision Tree
* Linear
* Random Forest
* LightGBM

![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/Screenshot%20from%202022-02-23%2000-03-50.png)

## [Decision Tree Classifier:](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/weatherpredictionclassifier.ipynb)

## [Forecasting:](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/WeatherForecast_SARIMA.ipynb)

Seasonal Autoregressive Integrated Moving Average (SARIMA)  or Seasonal ARIMA, is an extension of ARIMA that explicitly supports univariate time series data with a seasonal component. We have plotted the data, and  forecast using the confidence interval of 95%. So what we did step by step is as follows

1.Fit model parameters on a training sample
2.Produce h-step-ahead forecasts from the end of that sample
3.Compare forecasts against test dataset to compute error rate
4.Expand the sample to include the next observation, and repeat
