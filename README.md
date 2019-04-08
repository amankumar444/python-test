# python-test (first time working on time series data)
Suggestions are appreciated.

Time Series Analysis
Stock prices for TCS and INFOSYS and NIFTYIT Index.
Stock prices and OCLHV values are downloaded using pandas_datareader library and OCLHV(Opening Closing Low High Volume) values for Index NIFTY IT is downloaded using nsepy library.

Part - 1 
1) Moving Average of 4,16,...,52 weeks
2) Where rolling window is incremented with 10 steps
For all the stocks and index dataset starting from 10 to 80
3) Creation of dummy time series:
  - Volume shocks - If volume traded is 10% higher/lower than previous day
     - Dummy-coded time series for direction of shock
  - Price shocks - If closing price at T vs T+1 has a difference > 2%
     - Dummy-coded time series for direction of shock
  - Pricing shock without volume shock
  
Part - 2
Timeseries plot of close prices of stocks/indices with the following features:
1) Color timeseries in simple blue color
2) Color timeseries between two volume shocks in a different color (Red)
3) Color spectrum based on difference of 52 week moving average
4) Closing Pricing shock without volume shock to identify volumeless price movement
5) Autocorrelation plot for each stock/index on upto all lookbacks on bokeh

Part - 3
The goal is to to predict INFY,TCS and NIFTYIT index Prices for tomorrow.  Models that is choosen:

-
  1) Linear Regression 
  2) Lasso Regression(alpha -0.0001)
  3) Linear SVM (gives R^2 score = -3.7877538209787867, thus it was no further used)
  
- Checking for assumptions, for all data sets and Linear Models:
  1) RMSE of y_predicted with y_test(last 50 days Closing price of TCS, INFOSYS and NIFTYIT index)
  2) Jarque_Bera_Normality test was performed to check the Normal distribution of Residual
  3) Variance of the residual was also checked, to check the distribution of error
  4) Histogram was printed to check the dribution of residual graphically
  5) Scatter Plot of Residual and y_pred was drawn, to check Normality of error
  6) Correlation between Y(t-1)(X_training data set, produced from lag of 1 from original data set) and Correlation was done.
