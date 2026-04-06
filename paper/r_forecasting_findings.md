# R Forecasting Findings

## 1. Forecasting framework

This section uses univariate ARIMA models in R to forecast two quarterly UK mortgage-risk series: the serious mortgage arrears rate and new possessions. The final eight quarters of the sample were reserved as a test set, while the earlier observations were used for model training.

## 2. Serious arrears forecast

The selected ARIMA model for serious arrears was ARIMA(1,2,1). In the test period, the model produced an RMSE of 0.3227, an MAE of 0.2887, and a MAPE of 30.02%. These results indicate that the model captured the broad direction of the series but forecast accuracy was limited. In particular, the model tended to underpredict the later upward movement in serious arrears during the test period.

This result is useful because it establishes a univariate baseline. It suggests that serious arrears may not be well explained by past values alone, and that richer models using mortgage-market or macro-financial predictors may be needed for stronger forecasting performance.

## 3. New possessions forecast

The selected ARIMA model for new possessions was ARIMA(0,2,1)(1,0,1)[4]. In the test period, the model produced an RMSE of 440.2543, an MAE of 363.6301, and a MAPE of 18.93%. Compared with the serious-arrears forecast, this represents better predictive performance. This suggests that possession activity may display a stronger univariate time-series structure over the sample period.

## 4. Interpretation for the portfolio and paper

Taken together, the R forecasting results add a useful predictive layer to the project. They show that univariate ARIMA models can provide a baseline forecast, but predictive performance differs across mortgage-stress outcomes. Serious arrears were harder to forecast accurately using only their own past values, while new possessions showed more stable forecastability.

For the portfolio, this strengthens the project by showing that the analysis does not stop at descriptive and econometric modeling. It also includes a dedicated forecasting component using R. For the paper, these results can be used as a short forecasting section or robustness-style extension, showing how far standard univariate time-series models can explain UK mortgage stress.

