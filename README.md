# 📈 Stock Market Prediction Using Time Series Analysis

> Predicting short-term Apple (AAPL) stock prices using ARIMA and its subclasses — AR, MA, and ARMA — applied on historical time series data.

---

## 🧠 Overview

The stock market is one of the most unpredictable sectors of finance, involving a large number of investors, buyers, and sellers. While machine learning has introduced several forecasting techniques, very few have proven effective for stock market prediction due to its time-dependent nature.

This project leverages **Time Series (TS) Analysis** to predict short-term stock prices. Since time is a crucial factor in stock data, the **Autoregressive Integrated Moving Average (ARIMA)** model — widely used in financial and economic sectors — is applied for its efficiency and strong potential in short-term forecasting.

---

## ⚙️ Methodology

### 1. Stationarity Check
Before modeling, the historical stock data is tested for stationarity using:
- **Plotting Rolling Statistics** — visual inspection of rolling mean and standard deviation
- **Dickey-Fuller Test** — statistical test to confirm stationarity

### 2. Making the Series Stationary
If the series is non-stationary, the following transformations are applied to remove **Trend** and **Seasonality**:
- Log scaling
- Moving average subtraction
- Exponential decay weighted average
- Differencing (shift-based)

### 3. Model Fitting
Four models are fitted and compared:
| Model | Description |
|-------|-------------|
| **AR** | Autoregressive — uses past values |
| **MA** | Moving Average — uses past forecast errors |
| **ARMA** | Combination of AR and MA |
| **ARIMA** | ARMA with integrated differencing for non-stationary data |

### 4. Forecasting & Inverse Transformation
Predicted values from the log-scaled series are converted back to the original scale by reversing the log transformation, giving the final stock price forecasts.

---

## 📊 Dataset

- **Stock:** Apple Inc. (AAPL)
- **Source:** Historical AAPL stock data (`aapl.csv`)
- **Period:** November 1998 – November 2018
- **Records:** 5,033 trading days
- **Features:** Date, Open, High, Low, Close, Adj Close, Volume

---

## 🛠️ Tech Stack

- **Python 3.13**
- `pandas` — data processing
- `numpy` — numerical computation
- `matplotlib` — visualization
- `statsmodels` — ARIMA modeling and statistical tests
- `scikit-learn` — performance metrics (MSE)

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/Snevj/ARIMA-based-Stock-market-pridictor.git
cd ARIMA-based-Stock-market-pridictor
```

### 2. Create and activate a virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install pandas numpy matplotlib statsmodels scikit-learn
```

### 4. Run the analysis
```bash
python3 TimeSeriesAnalysis.py
```

---

## 📁 Project Structure

```
ARIMA-based-Stock-market-pridictor/
│
├── Dataset/
│   └── aapl.csv               # Historical AAPL stock data
│
├── TimeSeriesAnalysis.py      # Main analysis and prediction script
├── README.md
└── .gitignore
```

---

## 📉 Results

The ARIMA model successfully fits the AAPL stock price series after log transformation and differencing. Forecasted values are converted back to original scale and plotted against actual prices for visual comparison.

---

## 📌 Key Concepts

- **Stationarity** — A time series whose statistical properties (mean, variance) do not change over time
- **ARIMA(p, d, q)** — p: AR order, d: differencing order, q: MA order
- **ADF Test** — Augmented Dickey-Fuller test for stationarity
- **ACF/PACF** — Autocorrelation and Partial Autocorrelation plots used to determine optimal p and q values