# 🌍 World CO2 Emissions Forecasting

## 📈 Project Overview

This project aims to **forecast global CO2 emissions** using two popular time series modeling techniques: 
- **ARIMA (Autoregressive Integrated Moving Average)**
- **LSTM (Long Short-Term Memory) Neural Networks**

The dataset spans from **1750 to 2020**, sourced from *Our World in Data*, and includes the total CO2 emissions per year in tonnes.

---

## 🎯 Goals

- Model and forecast future CO2 emissions using statistical and deep learning techniques.
- Compare the performance, accuracy, and trade-offs of ARIMA and LSTM models.
- Understand environmental trends and contribute to climate change awareness.

---

## 🗃️ Dataset

- **Source**: [Our World in Data - CO2 Emissions](https://ourworldindata.org/co2-emissions)
- **Attribute Used**: `CO2` – Tonnes of CO2 emitted globally per year
- **Data Range**: 1750 – 2020 (271 yearly data points)

---

## 📊 ARIMA Model Highlights

- Applied log transformation + 1st order differencing for stationarity (ADF statistic << 1% critical value).
- Final model configuration: **ARIMA(p=1, d=1, q=1)**
- Cross-validated using **rolling forecasts** from 1820 to 2020.
- **MAPE consistently < 5%**, indicating excellent predictive power.
- Forecasted value for 2021: **33.7 Billion Tonnes** (7.2% under real IEA value).
- Advantages: Fast training, low resource demand, solid baseline forecasting.

---

## 🤖 LSTM Model Highlights

- Preprocessed data into fixed-length sequences using a sliding window approach.
- Scaled and split data into **92.5% training/validation** and **7.5% testing**.
- Model Architecture:
  - Two LSTM layers (145 and 95 neurons)
  - Fully connected dense layer (45 neurons)
  - Final output neuron
- Tuned using **Keras Tuner's Random Search** (21 min runtime on RTX 3060Ti).
- **MAPE < 2%** on test set; most error on 2020 (pandemic outlier).
- Forecasted value for 2021: **35.4 Billion Tonnes** (2.5% under real IEA value).
- Advantages: Captures long-term trends, higher precision with more data and compute.

---

## ⚔️ ARIMA vs. LSTM: Model Comparison

| Feature            | ARIMA                      | LSTM                            |
|-------------------|----------------------------|----------------------------------|
| Type              | Statistical Model          | Recurrent Neural Network         |
| Accuracy (2021)   | 33.7B (7.2% error)         | 35.4B (2.5% error)               |
| Training Time     | Very Fast                  | Moderately High (20+ minutes)    |
| Data Requirement  | Lower                      | Higher                           |
| Resource Demand   | Low                        | GPU preferred                    |
| Interpretability  | High                       | Moderate                         |

---

## 🧪 Evaluation Metrics

- **ADF Test** for stationarity check
- **AIC/BIC** for ARIMA model selection
- **MAPE** (Mean Absolute Percentage Error)
- **Visual trend analysis** for future forecasts

---

## 📅 Forecast Summary (2021–2030)

Both models forecast an **upward trend** in CO2 emissions:
- ARIMA: Constant high-rate increase
- LSTM: Upward trend with slight deceleration

**Forecasted emissions by 2030**: ~5.3 Billion Tonnes increase from 2020.

---

## 📘 References
Our World in Data: https://ourworldindata.org/co2-emissions

IEA Report 2021: https://www.iea.org/reports/global-energy-review-co2-emissions-in-2021

ARIMA: Duke University – Introduction to ARIMA

Deep Learning (Goodfellow, Bengio, Courville) – Chapter 10: Sequence Modeling

## 📢 Final Note
This project demonstrates how data science and machine learning can help us understand and predict critical environmental issues like climate change. Small efforts in code can contribute to big changes in awareness.

Let’s be responsible and data-driven for a better future 🌱


