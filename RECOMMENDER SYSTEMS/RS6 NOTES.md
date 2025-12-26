# Lecture: Introduction to Time Series Analysis

## 1. What is Time Series Data?

Time series data is a sequence of data points collected **over time** at regular intervals.

Key characteristic:
- Order of data matters
- Time dependency exists between observations

Examples:
- Daily stock prices
- Monthly sales data
- Hourly temperature readings
- Website traffic per day

Unlike normal tabular data, **time is a critical dimension** here.

---

## 2. Why Time Series Analysis is Important

Time series analysis helps us:
- Understand patterns over time
- Forecast future values
- Detect anomalies or sudden changes
- Support business decisions

Real-world use cases:
- Sales forecasting
- Demand prediction
- Stock market analysis
- Weather forecasting
- Server load prediction

---

## 3. Components of Time Series

A time series is generally made up of four components:

### 3.1 Trend (T)

Trend represents the **long-term movement** of data.

Examples:
- Increasing sales over years
- Decreasing production due to market decline

Trend answers:
> Is the data generally increasing, decreasing, or stable?

---

### 3.2 Seasonality (S)

Seasonality refers to **repeating patterns** at fixed intervals.

Examples:
- Higher sales during festivals
- Increased AC usage during summers
- Weekly traffic spikes on weekends

Seasonality is:
- Predictable
- Fixed frequency (daily, weekly, monthly, yearly)

---

### 3.3 Cyclic Pattern (C)

Cycles are similar to seasonality but:
- Do not have fixed duration
- Occur over longer periods

Examples:
- Economic booms and recessions
- Market cycles

Key difference:
- Seasonality is regular
- Cycles are irregular

---

### 3.4 Noise / Irregular Component (R)

Noise is random variation that:
- Cannot be predicted
- Does not follow a pattern

Examples:
- Sudden machine failure
- Unexpected news events

Noise is unavoidable in real-world data.

---

## 4. Time Series Decomposition

Time series decomposition means breaking the data into components:

Observed Data = Trend + Seasonality + Noise  
(Additive Model)

OR

Observed Data = Trend × Seasonality × Noise  
(Multiplicative Model)

Additive model is used when:
- Seasonal variations are constant

Multiplicative model is used when:
- Seasonal variations grow with time

---

## 5. Stationarity in Time Series

### 5.1 What is Stationarity?

A time series is **stationary** if:
- Mean is constant over time
- Variance is constant
- Autocovariance does not change with time

Why stationarity matters:
- Most forecasting models assume stationarity
- Non-stationary data gives poor predictions

---

### 5.2 Non-Stationary Data

Signs of non-stationarity:
- Trend exists
- Changing variance
- Seasonality present

Most real-world data is **non-stationary by default**.

---

## 6. Making a Time Series Stationary

Common techniques:

### 6.1 Differencing

Subtract previous value from current value:

Yₜ − Yₜ₋₁

This removes:
- Trend
- Some seasonality

---

### 6.2 Log Transformation

Apply log to stabilize variance.

Useful when:
- Values increase exponentially

---

### 6.3 Seasonal Differencing

Subtract value from previous season:

Yₜ − Yₜ₋ₛ

Where s = seasonal period

---

## 7. Autocorrelation in Time Series

Autocorrelation measures:
- Relationship between current value and past values

Example:
- Today's sales depend on yesterday’s sales

---

### 7.1 Autocorrelation Function (ACF)

ACF shows:
- Correlation between Yₜ and Yₜ₋ₖ for different lags k

Used to:
- Identify moving average components
- Detect seasonality

---

### 7.2 Partial Autocorrelation Function (PACF)

PACF shows:
- Direct relationship between Yₜ and Yₜ₋ₖ
- Removes indirect effects

Used to:
- Identify autoregressive components

---

## 8. Forecasting Objective

The goal of time series forecasting is:
- Predict future values using past observations

Good forecasting models should:
- Capture trend
- Handle seasonality
- Ignore noise as much as possible

---

## 9. Common Time Series Models (Preview)

Models discussed briefly (detailed in next lectures):
- Moving Average (MA)
- Autoregressive (AR)
- ARIMA (AR + I + MA)
- SARIMA (Seasonal ARIMA)
- Prophet
- LSTM (Deep Learning)

---

## 10. Real-World Business Perspective

Example:
- Predict next month’s sales using past 3 years data

Steps:
1. Visualize data
2. Identify components
3. Make data stationary
4. Choose model
5. Validate predictions

---

## 11. Summary

Key takeaways:
- Time series data is order-sensitive
- Trend, seasonality, cycles, and noise define behavior
- Stationarity is critical for modeling
- Decomposition helps understand data
- Forecasting is the final goal

---

## 12. What Comes Next

Next lecture will cover:
- Autoregressive (AR) model
- Moving Average (MA) model
- ARIMA in detail
- Mathematical intuition + examples
