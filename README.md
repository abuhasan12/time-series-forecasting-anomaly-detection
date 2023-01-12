# Anomaly Detection for Time Series Data using Auto-Regressive Forecasting

This notebook presents a method for detecting anomalies in time series data using auto-regressive forecasting. The dataset used in this project is a monthly record of airline passengers from the year 1949 to 1960. An anomaly was introduced in the data for the year 1958 (August).

![Anomaly](https://github.com/abuhasan12/time-series-forecasting-anomaly-detection/blob/main/readme_imgs/Anomaly.png)

## Data Exploration

The first step in the process is to explore the dataset. This includes decomposing the time series into trend, seasonality, and residuals. Additionally, stationarity was checked using the ADF test and the data was made stationary by performing a log transformation and differencing.

![Decomposition](https://github.com/abuhasan12/time-series-forecasting-anomaly-detection/blob/main/readme_imgs/Decomp.png)
![Differncing](https://github.com/abuhasan12/time-series-forecasting-anomaly-detection/blob/main/readme_imgs/Differenced.png)

## Auto-Regressive Models

To detect the anomaly, both ARMA and SARIMA models were used. The models were trained on the data prior to 1958 (75% of the original dataset) and the error for each trained data point was calculated. The massive error caused by the anomaly in 1958 was observed between the predicted and actual values.

![ACF](https://github.com/abuhasan12/time-series-forecasting-anomaly-detection/blob/main/readme_imgs/ACF.png)
![PACF](https://github.com/abuhasan12/time-series-forecasting-anomaly-detection/blob/main/readme_imgs/PACF.png)

## Forecasting

A SARIMA model was trained on the data prior to 1958 (75% of the original dataset) and used to make forecasts for the years 1958, 1959 and 1960. These forecasts were then compared to the actual values (the last 25% of the original dataset) to detect the anomaly as the deviation between the predicted results and the actual results (the error).

![Forecasting](https://github.com/abuhasan12/time-series-forecasting-anomaly-detection/blob/main/readme_imgs/Predictions.png)

## Conclusion

This notebook presents a method for anomaly detection in time series data using auto-regressive forecasting. The dataset used in this project is a monthly record of airline passengers from the year 1949 to 1960. The anomaly was introduced in the data for the year 1958 (August) and detected using ARMA and SARIMA models by comparing the predicted values to the actual values and observing the deviation caused by the anomaly. It's important to note that there are other ways to anomaly detect in time series data such as isolation forest, neural networks (LSTM) etc. but this project focuses on using this method.