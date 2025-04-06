# assignment-5---ARIMA
Performing ARIMA on my time series
Series: ts_price
ARIMA(0,1,1) 

Coefficients:
          ma1
      -0.7218
s.e.   0.1208

sigma^2 = 236.2:  log likelihood = -170.06

# Explain Output
The ARIMA(0,1,1) model was selected as the best fit for the house price time series based on automated model selection using AIC. This model applies first-order differencing to remove underlying trends and includes a single moving average term with a coefficient of -0.7218, indicating that current values are influenced by the previous forecast error in the opposite direction. The MA term is statistically significant, supported by a low standard error of 0.1208. The residual variance is 236.2, and the model fit statistics—AIC (344.13), AICc (344.44), and BIC (347.56)—confirm that the model adequately captures the structure of the data. Overall, the ARIMA(0,1,1) model is a strong choice for forecasting house prices in the short term.

# Run Residual Analysis
The residual analysis of the ARIMA(0,1,1) model indicates that the model provides a good fit for the data. The histogram of residuals shows an approximately normal distribution centered around zero, suggesting that the model's forecast errors are unbiased. Additionally, the Ljung-Box test returned a p-value of 0.8509, indicating no significant autocorrelation in the residuals. This is further supported by the absence of any strong patterns or spikes in the autocorrelation function (ACF) plot. Overall, the residuals behave like white noise, which confirms that the ARIMA model has effectively captured the underlying structure of the time series and that its assumptions are reasonably satisfied.

# Perform and Plot for Next 5 Periods
  Point Forecast    Lo 80    Hi 80    Lo 95     Hi 95
43       67.75063 48.05479 87.44646 37.62845  97.87281
44       67.75063 47.30662 88.19463 36.48422  99.01703
45       67.75063 46.58489 88.91637 35.38042 100.12084
46       67.75063 45.88696 89.61429 34.31304 101.18822
47       67.75063 45.21064 90.29062 33.27869 102.22257

# Show Accuracy of ARIMA Model
using accuracy(auto_fit)
RMSE - 14.99836
MASE - 0.7496724
ACF1 - 0.05350284
