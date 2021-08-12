
# Cryptocurrency Interactive Visualization and Forecast

This project aims to develop interactive visualizations of many Crypto coins and Forecast the future prices using ARIMA. The interactive visualizations are made using the Plot.ly library, and the Forecast uses the ARIMA model for prediction.

The historical prices data for Bitcoin, Ethreum, Monero, Chainlink, Binance Token and Dogecoin is obtained from CoinGecko.com. The data is available from the time the coins are added to CoinGecko.

The interactive visualizations are done using the Plot.ly library which enables to filter the data by time and coin, and then to zoom in and see price movements up to a daily range. Historical price comparison and Daily price change/ volatility charts are made. The correlation between BTC and altcoins, and between coins are also looked at.

The forecast for LINK is done using ARIMA by looking at different aspects of data like Seasonality, Trend, Noise, Residuals, etc. The model cannot be used to make real-world investment decisions, primarily due to the high volatility of the coins.

### Contents
1. Import Libraries

2. Load Data

3. Data Cleaning

4. Historical Price Visualization
4.1 Data Preparation\
4.2 Daily Historical Price Chart Since Existence of the Coin\
4.3 Daily ROI Chart

5. Price Correlation

6. Forecasting Price with ARIMA for LINK
6.1 Prepare Data\
6.2 Check for Stationarity of the Data\
6.3 Pre-processing: Transformation and Differencing\
6.4 Autocorrelation\
6.5 ARIMA Model\
6.6 Predictions\
6.7 Evaluation

7. Observations

8. References
## 🛠 Skills
Python, Pandas, Matplotlib, Seaborn, Plotly, statsmodels, ARIMA, time-series analysis

  
## Visualization Example

![Historical Prices](https://github.com/uvaise-n/Cryptocurrency-Interactive-Visualization-and-LINK-Forecast/blob/main/Historical%20Prices.gif "Historical Prices")



## Observations 

#### Data
- The number days of exsistence (or since coin gecko collected historical information) can be seen from the shape of data. With BTC having the longest and DOGE being the recent

![Correlation](https://github.com/uvaise-n/Cryptocurrency-Interactive-Visualization-and-LINK-Forecast/blob/main/Correlation.JPG)
- All coins have a very high correlation to Bitcoin and between each other. Chainlink and Ethereum have a surprisingly high correlation to Bitcoin.
- The Price change however doesn't have a very high correlation.
- We could visualize the correlation using a Pairplot
![Pairplot](https://github.com/uvaise-n/Cryptocurrency-Interactive-Visualization-and-LINK-Forecast/blob/main/Pairplot.JPG)

#### Forecast
![Forecast](https://github.com/uvaise-n/Cryptocurrency-Interactive-Visualization-and-LINK-Forecast/blob/main/Forecast.JPG)
- The data for LINK has an upward trend and a seasonality separated by year. The residuals were fairly constant until mid-2020 and since then are very volatile. This reduces the quality of the forecast.
- We see that the 3 month and second-order differentiation of 12 months, both with box cox transformation makes the data stationary
- The model we used is still not stationary as we used the orginal monthly data and not the pre-processed ones.
- The pre-processed data is supposed to be used to build the model and do the prediction. However, they weren't capturing the seasonality well enough to give a forecast better than a straight line or a squiggly line.
- The model can't be used to make investment decisions, esp because it is used to predict long periods.


#### Potential Improvements 
1. The model can be made better by incorporating the seasonal trends with the help of a domain expert. Due to the high volatility of cryptocurrencies the seasonality however may be difficult to determine and could make ARIMA not a great model for crypto forecast.
2. The model can be made better with the use of standardization and differentiation techniques
3 By avoiding periods of high volatility
4. Using models other than ARIMA

## Acknowledgements

 - [Data from CoinGecko](https://www.coingecko.com/en/coins/chainlink/historical_data/usd#panel)
 - Introduction to Time Series Forecasting by Jason Brownlee (Machine Learning Mastery) 
 - [ARIMA Temperature Forecasting](https://github.com/nachi-hebbar/ARIMA-Temperature_Forecasting)
 - [Cryptocurrency Price Forecasting](https://www.kaggle.com/taniaj/cryptocurrency-price-forecasting/)
 - [ARIMA And Seasonal ARIMA](https://github.com/krishnaik06/ARIMA-And-Seasonal-ARIMA)
 - [Stock Market Forecasting Time Series Analysis](https://www.kdnuggets.com/2020/01/stock-market-forecasting-time-series-analysis.html)
 - [Time-series forecasting methods in Python](https://machinelearningmastery.com/time-series-forecasting-methods-in-python-cheat-sheet/)
 - [Create and embed plotly visualization](https://towardsdatascience.com/how-to-create-a-plotly-visualization-and-embed-it-on-websites-517c1a78568b)
