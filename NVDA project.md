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

# Key results

Descriptive statstics
| Metric            | NVDA    |
| ----------------- | ------- |
| Mean Daily Return | 0.37%   |
| Std Deviation     | 3.13%   |
| Min Daily Return  | -16.97% |
| Max Daily Return  | 24.37%  |

Value at Risk (95% Confidence)
| Metric                  | NVDA   |
| ----------------------- | ------ |
| Historical VaR          | -4.14% |
| Monte Carlo VaR         | -4.75% |
| Expected Shortfall (ES) | -6.20% |

Rolling 60-Day VaR

Mostly between -3.27% and -3.83%, slight increase in late Feb 2026

Highlights dynamic risk trends over time

# Visualizations

Rolling 60-Day VaR

Mostly between -3.27% and -3.83%, slight increase in late Feb 2026

Highlights dynamic risk trends over time

# Key Conclusions

- NVDA exhibits moderate daily volatility (~3.1%) with rare extreme losses up to -16.97%.
- 95% Value-at-Risk (VaR): Historical -4.14%, Monte Carlo -4.75%
- Expected Shortfall (ES): -6.20%, highlighting tail risk for worst-case days
- Rolling 60-day VaR identifies periods of elevated risk, often matching AI, earnings, or regulatory events.
- Compared to Apple, NVDA shows higher volatility and downside risk, emphasizing the need for position sizing and hedging strategies.
- The analysis provides quantitative tools for informed portfolio risk management.

# References / Data Sources

- Yahoo Finance (yfinance)
- Bloomberg, CNBC, Wall Street Journal
- Python libraries: pandas, NumPy, matplotlib

Comparison with Apple (AAPL) for volatility context
