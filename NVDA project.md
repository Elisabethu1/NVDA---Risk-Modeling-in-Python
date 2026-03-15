# NVDA - Risk-Modeling-in-Python

# Project Description

This project analyzes NVIDIA (NVDA) stock daily risk from Jan 2023 – Mar 2026. Using Python and historical stock data from Yahoo Finance, it calculates:
- Daily returns and descriptive statistics
- Historical Value-at-Risk (VaR)
- Monte Carlo VaR simulations
- Expected Shortfall (ES)
- Rolling 60-day VaR to capture dynamic risk trends
  
The goal is to quantify potential losses and provide actionable insights for investors and portfolio managers.

# Sample code

import yfinance as yf
import numpy as np
import pandas as pd

Download NVDA stock data
nvda = yf.download('NVDA', start='2023-01-01', end='2026-03-01', auto_adjust=True)

Compute daily returns
nvda['Return'] = nvda['Close'].pct_change().dropna()

Historical VaR (95%)
VaR_hist = nvda['Return'].quantile(0.05)

Monte Carlo VaR
mu = nvda['Return'].mean()
sigma = nvda['Return'].std()
simulations = np.random.normal(mu, sigma, 100000)
VaR_mc = np.percentile(simulations, 5)

print(f"Historical VaR: {VaR_hist:.2%}, Monte Carlo VaR: {VaR_mc:.2%}")

Full code and calculations are available in the notebook: NVDA - Daily Risk Modeling.ipynb.

# Project Files
NVA - Daily Risk Modeling.ipynb → Python notebook with full code and visualizations
images/ → folder with charts (closing price, rolling VaR, daily returns histogram)
NVDA_Risk_Report.pdf (optional) → full written report

# Topics covered / Visualizations
Descriptive Statistics: mean, standard deviation, min/max daily returns

Risk Metrics: Historical VaR, Monte Carlo VaR, Expected Shortfall (ES)
Rolling Risk Analysis: 60-day rolling VaR
Graphs / Visualizations:
NVDA closing price over time
Rolling 60-day VaR
Daily returns histogram with VaR & ES highlighted

Optional: Comparison with Apple (AAPL) for volatility context
