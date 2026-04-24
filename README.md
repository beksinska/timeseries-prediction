Time series forecasting is the task of predicting future values based on
past observations. In this project, temperature values were predicted
using only historical temperature data, a setup known as univariate
forecasting. Univariate forecasting considers a single variable as the
input feature to predict the target variable, making it a
straightforward and practical approach. However, the simplicity of the
univariate setup also comes with limitations. In cases where the target
variable is influenced by multiple external factors, relying solely on
historical values can lead to suboptimal predictions.

The purpose of this study is to compare traditional statistical methods
with modern deep learning approaches for temperature prediction.
Seasonal Autoregressive Integrated Moving Average (SARIMA), and Long
Short-Term Memory (LSTM) models were used to investigate which method
best captures the underlying patterns in the temperature time series.

The data from Berlin, Tempelhof were used for model training and predictions. The data were provided by ECA&D project.

# Related Literature

Time series prediction involves analyzing sequential data points
collected over time to forecast future values. This type of data is
common in domains such as finance, weather forecasting, energy, and
healthcare. The temporal structure of time series data makes forecasting
a challenging task, especially when dealing with non-linear trends,
seasonality, and data drift. [Alsharef2022]

Machine Learning (ML) techniques have become increasingly popular for
forecasting time series due to their ability to capture complex patterns
beyond the capabilities of traditional statistical methods. These models
offer advantages in prediction accuracy. However, they also require
careful tuning. 

Traditional approaches to time series forecasting include statistical
models such as Autoregressive (AR), Moving Average (MA), Autoregressive
Moving Average (ARMA), and ARIMA. These models assume linear
relationships and stationary data, which limit their effectiveness when
applied to evolving data. [Alsharef2022]

In contrast, ML methods like Recurrent Neural Networks (RNN), LSTM,
Gated Recurrent Unit (GRU), and Independent RNN (IndRNN) are designed to
handle sequential data and are capable of learning non-linear
dependencies. These models often outperform classical approaches when
properly tuned. [Alsharef2022]

ML has significantly advanced the field of time series prediction,
enabling models to capture complex patterns. However, achieving optimal
performance still requires substantial expertise and tuning. 

# Method

Two different models for temperature forecasting were trained on monthly mean temperature data and compared.

The ARIMA model is a classical approach for time series prediction.
ARIMA models the future value on the basis of past values and past
errors. The statsmodels Python library was used to fit an ARIMA model.
Since temperature data usually has seasonal patterns, a seasonal ARIMA
(SARIMA) model was applied.

The LSTM network is a deep learning model built to handle sequences. It
can learn long-term dependencies in the data better than traditional
models. [Hochreiter1997]

Both models were evaluated using Root Mean Square Error (RMSE) to
measure average prediction error, and R² Score to measure how well the
model explains the variance in the data.

# Results

Models were evaluated on a test dataset, which included temperature values starting from 2024. The SARIMA model achieved a lower RMSE and a higher R²
compared to the LSTM model. This indicates that, for this particular
univariate dataset, the SARIMA model was able to fit the data slightly
better and predict more accurately.


*Comparison of forecasted with SARIMA model and observed monthly mean
temperatures*

![Comparison of forecasted with SARIMA model and observed monthly mean
temperatures](assets/sarima.png)


*Comparison of forecasted with LSTM model and observed monthly mean
temperatures*

![Comparison of forecasted with LSTM model and observed monthly mean
temperatures](assets/lstm.png)

Plots of predicted vs. true temperature values show that the SARIMA
model tracked the actual temperature trends more closely, than LSTM
model.

# Discussion

In this project, SARIMA model was able to predict future temperatures
well based only on historical temperature data. SARIMA performed better
than LSTM in terms of both RMSE and R² Score.

This suggests that when working with purely univariate time series that
have strong autocorrelation and seasonality, classical statistical
models like SARIMA can outperform more complex deep learning approaches.

Nonetheless, LSTM remains a powerful model, especially when more
features or nonlinear patterns are present. For future work, adding
additional meteorological variables might improve the LSTM performance
further.

# References

I acknowledge the data providers in the ECA&D project.
Klein Tank, A.M.G. and Coauthors, 2002. Daily dataset of 20th-century surface air
temperature and precipitation series for the European Climate Assessment. Int. J. of Climatol.,
22, 1441-1453.
Data and metadata available at https://www.ecad.eu

Alsharef, A., Sonia, Kumar, K., & Iwendi, C. (2022). Time series data modeling using advanced
machine learning and automl. Sustainability 2022, Vol. 14, Page 15292, 14, 15292.
https://doi.org/10.3390/SU142215292

Hochreiter, S., & Schmidhuber, J. (1997). Long short-term memory.

