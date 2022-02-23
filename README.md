# **FormulaAI-WeatherPrediction:**
Our solution is an AI-enabled weather forecasting application based on big data analysis to help Formula-1 drivers, investors, and betters make intelligent and context-aware decisions for successful racing and investments.

## 1. **System Architecture:**

ur Architectural Flow is divided into 3 main Activity:
1. Data Analytics
2. Oracle Cloud
3. Machine Learning Pipeline.  

We have a total 3572328 number of records that we used for our preliminary analysis, where we analyzed and investigated the data sets, and summarized their main characteristics.  
Which we later used to extract the top most features. We then used these selected feature with our Oracle Analytical Cloud​ and Oracle Autonomous Database. Since data was huge to work on files, we have resolved to use an autonomous database along with​ Oracle Data Science Cloud notebook. 


![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/FormulaAI-ActivityDiagram.drawio.png)

## 2. **Exploratory Data Analysis:**
[![](https://img.shields.io/badge/View%20on%20Github-%E2%86%A9-blue)](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/WeatherFormulaAIEDA.ipynb)

Yous can checkout the the complete notebook for complete lifecycle of exploratory data analysis in this repository.
### 1. Data Preprocessing:

Whether it is AI or ML, the foundation is data and lots of it. Every business has this data in one form or the other but it has to be cleaned and prepared into a state that can be used by Machine Learning to learn from. Data sources for a business can be both proprietary as well as from open sources such as weather data, traffic data etc.
 Business owned data can be numeric(loan amount, customer retention rate), categorical(gender, color, property type), time stamped (how many products were purchased in a time range) or even free text (think emails, doctor’s notes)
For our current analysis the data has a total of 58 features, with 11 features with highest missing values, while 7 of them with single missing values that we are imputation later on.
The Next Steps is Statistical Analysis.

### 2. Statistical Analysis:
Statistics is used in a variety of sectors in our day-to-day life for analyzing the right data.
Define your question, Collect the right data, Understand the data, Cleaning the data, Analyze the data and finally interpret the results for the questions.

	- Pearson correlation
	- Statistical Summary
  
 ### 2. Feature Extraction:
Feature selection is to reduce the number of input variables when developing a predictive model. It is desirable to reduce the number of input variables to both reduce the computational cost of modeling and, in some cases, to improve the performance of the model. The feature importance (variable importance) describes which features are relevant. Random Forests are often used for feature selection in a data science workflow. The reason we used it here is because the tree-based strategies used by random forests naturally ranks by how well they improve the purity of the node. This means a decrease in impurity over all trees. 
So, There is 10 features/attributes whose importance is above the threshold.
We used the following 2 methods for Feature Extraction and got the same set of metrics as stated below:
1. KBest Method
2. Random Forest

These are the 10 selected features and their feature importance score.
| Feature                   | Score             |
| :---                      | :---:             |
| M_SESSION_UID             |   3.858013e+23    |
| M_SESSION_LINK_IDENTIFIER |   3.788487e+14    |
| M_WEEKEND_LINK_IDENTIFIER |   3.788487e+14    |
| M_SEASON_LINK_IDENTIFIER  |   3.788487e+14    |
| M_SESSION_DURATION        |   9.514273e+08    |
| M_FRAME_IDENTIFIER        |   9.229148e+08    |
| M_SESSION_TIME_LEFT       |   1.304397e+08    |
| TIMESTAMP                 |   1.027454e+08    |
| M_TRACK_LENGTH            |   7.654119e+07    |
| M_SESSION_TIME            |   4.096546e+07    |


## 3. **Selection of Classifier based on AUTO ML results:**(
[![](https://img.shields.io/badge/View%20on%20Github-%E2%86%A9-blue)](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/AUTOML_ClassificationSelection.ipynb)

* Decision Tree
* Linear
* Random Forest
* LightGBM

![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/Screenshot%20from%202022-02-23%2000-03-50.png)

## **4. Weather Classification:**
[![](https://img.shields.io/badge/View%20on%20Github-%E2%86%A9-blue)](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/weatherpredictionclassifier.ipynb)   
For the classification model, we shortlisted 4 models, Decision Trees, Random Forest, Logistic Regression, and Light GBM. Based on the results of Auto ML we selected Decision Trees for the classification task to keep our solution less resource extensive and time efficient.
## **5. Forecasting:** 
[![](https://img.shields.io/badge/View%20on%20Github-%E2%86%A9-blue)](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/WeatherForecast_SARIMA.ipynb)

Seasonal Autoregressive Integrated Moving Average (SARIMA)  or Seasonal ARIMA, is an extension of ARIMA that explicitly supports univariate time series data with a seasonal component. We have plotted the data, and  forecast using the confidence interval of 95%. So what we did step by step is as follows

1. Fit model parameters on a training sample
2. Produce h-step-ahead forecasts from the end of that sample
3. Compare forecasts against test dataset to compute error rate
4. Expand the sample to include the next observation, and repeat


## **6. Output:** 
### Decision Tree with Selected Feature in EDA:
![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/decision-tree.png)

### RandomForest for Prediction:
![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/RandomForest.png)

### Final Output:

```python
{
  '5':{
    'type': 1,
    'rain_percentage': 0.074
  },
  '10':{
    'type': 0,
    'rain_percentage': 0.0269
  }
  '15':{
    'type': 1,
    'rain_percentage': 0.0150
  }
  '30':{
    'type': 0, 
    'rain_percentage': 0.00508
  }
  '50':{
    'type': 0,
    'rain_percentage': 0
  }
} 
```


## **7. Prototype:** 
This is our sample dashboard where users would be able to see the real time change in forecasting, 

![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/image2.png)


![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/Slide13.jpg)

The changes would be visible for every 5 till 60 minutes, all the while updating the total metrics affecting the forecasting, realtime nowcast precipitation level and downpour change in the last few minutes . 

![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/Slide15.jpg)

The users would in fact be able to view the change in the values for the metrics affecting the forecasting.

![My Remote Image](https://github.com/YousraMashkoor/FormulaAI-WeatherPrediction/blob/master/images/Slide17.jpg)