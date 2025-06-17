# Applied-Forecasting

# ⏳ NYC Temperature Forecasting (1869–2022)

A comprehensive project on time series forecasting using classical statistical models (ARIMA, SARIMA) and deep learning models (RNN, LSTM, GRU) to analyze over 150 years of daily temperature data recorded in Central Park, New York City.

---

## 📌 Project Overview

This repository contains the code and analysis for forecasting daily temperatures in NYC from 1869 to 2022. The project compares traditional statistical models and modern deep learning approaches for one-step temperature prediction, with the goal of identifying long-term seasonal patterns and evaluating model performance.

---

## 📁 Repository Contents

📦 Applied-Forecasting
├── 202201460_21.ipynb # Full code: data prep, classical models, and DL models
├── 202201460_21.pdf # Detailed report with visuals and interpretation
├── NYC_Central_Park_weather_1869-2022.csv # dataset used
├── requirements.txt
└── README.md # This file

## 🧪 Methods Used

### 📈 Classical Models
- AR (Autoregressive)
- MA (Moving Average)
- ARMA (Autoregressive Moving Average)
- ARIMA
- SARIMA (with seasonal order of (1,1,1,52))

### 🤖 Deep Learning Models
- RNN (Vanilla Recurrent Neural Network)
- LSTM (Long Short-Term Memory)
- GRU (Gated Recurrent Unit)


## 🗂 Dataset

**Source:** : https://www.kaggle.com/datasets/danbraswell/new-york-city-weather-18692022/data 
**Range:** 1869 to 2022  
**Key Features:**
- `TMIN` / `TMAX` → Used to compute `TEMP` (average temperature)
- `SNOW`, `PRCP`, `SNWD` → Used in EDA but not for forecasting

## 📊 Evaluation Metrics

Each model is evaluated using:
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score


## 🧹 Data Preprocessing Steps

- Filled `TMIN`, `TMAX` missing values using median
- Computed `TEMP = (TMIN + TMAX) / 2`
- Dropped `SNWD` due to excessive missingness
- Created normalized sliding and non-overlapping windows
- Chronologically split into 70/20/10 (Train/Val/Test)


## 🧠 Deep Learning Strategy

- **Window Size:** 30 days
- **Forecasting:** One-day ahead prediction (one-step)
- **Architecture:** 1 recurrent layer → dropout → dense layer
- **Tuning:** Grid search on units, dropout, batch size, and learning rate
- **Scaling:** MinMax normalization



## 📌 Key Takeaways

- **SARIMA** achieved the best performance for long-term seasonality.
- **GRU** outperformed RNN and LSTM in DL-based models.
- Non-overlapping windows improved generalization.
- Data normalization and correct temporal splitting are crucial.


## 👨‍💻 Authors

- **Tirth Chaudhari**  
  B.Tech in Mathematics and Computing, DAIICT

- **Shreya Patel**  
  B.Tech in Information and Communication Technology, DAIICT

## 📄 License
This project is for academic and educational use. Please cite appropriately if reused.
