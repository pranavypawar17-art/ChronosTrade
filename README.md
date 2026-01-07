# Chronos Trade 📈
### Multi-Modal Stock Market Prediction using ARIMA and LSTM

## Overview
Chronos Trade is a time series forecasting project focused on predicting stock prices
using both statistical and deep learning approaches.

In this project, ARIMA (AutoRegressive Integrated Moving Average) and LSTM
(Long Short-Term Memory) models are implemented and compared to forecast the
closing price of Google (GOOGL) stock using historical data obtained from Yahoo Finance.

---

## Objectives
- Understand and implement statistical and deep learning–based time series models
- Compare ARIMA and LSTM in terms of assumptions, behavior, and performance
- Gain practical insight into challenges of real-world financial time series forecasting

---

## Models Implemented

### ARIMA Model
ARIMA is a statistical time series forecasting model composed of:
- **AR (AutoRegressive):** Uses dependency between current and past values
- **I (Integrated):** Applies differencing to achieve stationarity
- **MA (Moving Average):** Uses past forecast errors

The model is represented as **ARIMA(p, d, q)**.
In this project, the optimal configuration obtained was:

**ARIMA(0,1,0)**  
This corresponds to a random walk model with first-order differencing.

---

### LSTM Model
LSTM is a type of Recurrent Neural Network (RNN) designed to model long-term
dependencies in sequential data.

Key characteristics:
- Does not require stationarity
- Learns non-linear relationships directly from data
- Uses memory cells with forget, input, and output gates
- Computationally intensive but powerful for complex patterns

---

## Statistical vs Deep Learning Approaches

| Aspect | ARIMA | LSTM |
|------|------|------|
| Data Assumption | Requires stationarity | No stationarity required |
| Pattern Type | Linear | Non-linear |
| Interpretability | High | Low |
| Computational Cost | Low | High |
| Performance on Volatile Data | Limited | Strong |

---

## Important Concepts Explained

### Stationarity and Differencing
A time series is stationary if its mean, variance, and autocovariance remain constant
over time. Since stock prices are usually non-stationary, differencing is applied:

Y′ₜ = Yₜ − Yₜ₋₁

This helps stabilize the mean and makes the data suitable for ARIMA modeling.

---

### ACF and PACF Plots
- **ACF (Autocorrelation Function):** Used to identify MA(q)
- **PACF (Partial Autocorrelation Function):** Used to identify AR(p)

These plots guided the selection of ARIMA parameters.

---

### Sliding Window Technique (LSTM)
LSTM requires supervised learning data.
A sliding window converts time series into:
- Input: past *n* time steps
- Output: next time step

This enables the model to learn temporal dependencies.

---

### Data Normalization
Min-Max normalization was applied before training the LSTM model:

X_norm = (X − X_min) / (X_max − X_min)

Benefits:
- Faster convergence
- Stable gradients
- Prevents dominance of large values

Normalization was performed using training data only to avoid data leakage.

---

## Implementation Challenges

### ARIMA
- Achieving stationarity required careful differencing
- ACF/PACF-based parameter selection was sometimes ambiguous
- Performance degraded during highly volatile periods

### LSTM
- Long training times
- Sensitive to hyperparameters (look-back window, batch size, learning rate)
- Risk of overfitting without validation
- Requires reshaping data into 3D format

---

## Observations and Results
- ARIMA(0,1,0) was suitable for short-term forecasting
- LSTM produced smoother and more stable forecasts
- LSTM residuals were more randomly distributed, indicating a better fit
- Learning curves showed steady loss reduction with controlled overfitting

---

## Technologies Used
- Python
- NumPy
- Pandas
- Matplotlib
- Statsmodels
- TensorFlow / Keras

---

## Future Improvements
- Use Bidirectional LSTM or GRU
- Incorporate technical indicators (RSI, MACD, volume)
- Add sentiment analysis and exogenous variables
- Perform hyperparameter optimization
- Implement a hybrid ARIMA + LSTM model

---

## Author
**Pranav Pawar**  
WiDS | 24B2503  
Midterm Project
