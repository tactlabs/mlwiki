/ [Home](../index.md) / [ML Archve](index.md)

# How to Choose a Forecasting Model

**Note:** Decision tree to select a time-series methodology

Key takeaways:

* When dealing with time series, classical statistical methods are not directly applicable, so make sure to use a time series-specific methodology
* Understanding the business problem and the data are crucial to select the most suitable model
* Choosing the model is just the start of an exciting journey of model training, evaluation, improvement and operations

Introduction

Forecasting is a vital function for any business operating in volatile environments. Capturing the variability of the economy and future demand is a crucial skill to react fast to changes and adjust the operations within the supply, procurement, logistics and others. The benefits of forecasting include cutting costs of stock keeping, reducing waste, decreasing out-of-stock and achieving higher service levels.

Time series analysis is a specific methodology that can help businesses improve their forecasting capabilities. It analyzes a sequence of equally spaced data points collected over an interval of time to extract meaningful statistics of the data and predict its future values.

However, with the increasing popularity of data science and the growing complexity of the data, the number of possible time-series models can be overwhelming. Do you need a simple solution to best capture historical sales or is your business strongly dependent on the number of external factors that need to be considered? These are example questions that need to be asked during the data exploration, to select the best-fitting model for the analytical problem. In this article, we will present our approach to perform time-series modeling, including analytical problem framing, data exploration and our novel framework for time-series model selection.

1. Analytical problem framing

In the first stage of our approach, the business problem is translated into an analytical problem and consequently, the scope is defined. This step is crucial to set up the approach of the analysis. In general, analytical problem framing includes defining hypotheses to be tested, variables to be extracted and success criteria for the overall solution. However, time series analysis requires additional steps which extend the standard AI methodology.

In general, the overall goal of time series solution is to minimize the error of the forecast. This can be translated to the business as avoided costs from unnecessary inventory or last-minute freight by increasing the accuracy of the demand forecast. Defining this goal analytically is important and will determine the variables of interest, the time horizon, the forecast granularity and the data hierarchy.

Time horizon is defined as the period of time for which we are forecasting data. For example, a procurement team needs to make an order for a specific number of materials 10 weeks in advance. In that case, the forecast horizon is at least 10 weeks, with 10 weeks probably providing the best accuracy. Based on the business problem, it is important to choose the right time horizon to receive actionable insights from the solution at the right time.

Forecast granularity is defined as the time dimension in which the data is formatted for the forecast, e.g. weekly, monthly or annual. For example, a weekly forecast will require sub-week forecast granularity to include the patterns in the data. The granularity should also be decided to gain the best insights but can also be impacted by data availability.

Product hierarchy is important to understand before starting a forecasting analysis on data. The choice of an optimal hierarchy is determined by the business problem but also by the availability of data. For example, if products are changing regularly but their compositions are highly similar, it can be interesting to group similar products and forecast these together

2. Data exploration and requirements

Data exploration typically consists of splitting the data into a training and testing set, outlier detection and identifying missing values. These steps are also performed with time series data but additional steps are required in order to start modeling.

When using time series data, it is important to detect any time-related pattern in the data which can help in understanding the problem at hand and choosing the model later. Seasonal patterns are present in time series when seasonal factors affect the data such as days in the week[1]. By plotting the data or by seasonal decomposition in the data exploration stage, it is possible to identify these patterns more clearly.

Feature engineering is a step that can have a large impact on the quality of the model. In time series there are different types of features that can be engineered, such as date time features, lag features and rolling window statistics. See a great article on feature engineering for time-series models[2].

In addition to historical data, there can be other external factors that can help in better predicting the future. We call these variables “external factors”. In this data exploration phase, it is important to identify these variables, understand them and transform them to fit the model. For example, car sales can help predict the demand for car parts. By adding this external factor to the explanatory variables, the performance of the forecasting model can improve.

3. Choosing a model

Time series data has many characteristics that influence future values, therefore we have created a decision tree to help choose the best fitting model. Here an example on how to use the decision tree:

First, you check how many data points are in your dataset. Our rule of thumb is that the dataset should contain at least 2 forecast periods. If that is not the case, you need to collect more data.

If you have enough data, stationarity is evaluated. Stationary data is defined as having a constant variance and mean over time. You can run an Augmented Dickey-Fuller (ADF) test to check this statistically, but you can also see it visually when plotting the data over time. To achieve stationarity, use the difference between observations at time t and t-1 instead of the observation at time t.

Next, you will need to identify the seasonality of the data. By decomposing your time series data, you will identify the trend, seasonal patterns and residuals of the data. The most common method is the classical seasonal decomposition method but there are also others (e.g. X11 decomposition, SEATS decomposition). If your data is not seasonal, you can choose between ARMA(X) and Exponential Smoothing, depending on if you need to add external variables to the model.

If your data is not stationary, checking if the trend is linear is necessary to choose between linear and non-linear models. In non-linear time series, the current value of the series is not a linear function of past observations. BDS test, when applied on residuals from the linear model, can detect a presence of omitted non-linear structure. However, just like with classical regression analysis, non-linearity of the data can be omitted by the transformation of the forecast or predictor variables (e.g. log()). Additionally, piece-wise linear analysis can be performed if non-linear data can be divided into linear periods. Nevertheless, non-linear models, incl. the ones based on ensemble modeling or neural networks, are known for their high performance and allow for incorporation of external variables in the forecasting, which can help with interpretation of the results.



4. Model performance and operations

There is a number of great articles on time-series assessment metrices and we recommend reading those [3–5]. Additionally, custom metrics can be designed that work best in a certain organization and can be easily interpreted by business stakeholders. Your forecasting model can also be benchmarked against simpler methods, like naive forecast or moving average.

Forecasting is done using historical data, and as it often happens in machine learning using a model trained once will lead to an increasing error over time. Model lifecycle monitoring is crucial to spot the decrease in performance on time and out-of-sample forecast is a useful methodology to circumvent it, by training the model with a rolling window over time.

Finally, it’s important to remember that choosing a model is just the beginning of the process. Thorough experimentation and subsequent model improvements will ensure it is as accurate as possible. Operationalization of the model needs to be considered, including how it will be integrated into existing systems and business processes.

Conclusion

Time-series modeling is an essential skill for various businesses. By understanding the business problem and the data, selecting the most suitable model, training and evaluating the model, and iteratively improving and operationalizing it, businesses can improve their forecasting capabilities and make better data-driven decisions. We hope that by following these steps and using a systematic approach, you can choose a forecasting model that meets the needs of the business and helps you make more accurate forecasts.

https://towardsdatascience.com/how-to-choose-a-forecasting-model-fa9c4a2e75b8