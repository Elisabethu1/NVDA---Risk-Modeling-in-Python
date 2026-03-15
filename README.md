# NVDA---Risk-Modeling-in-Python

Description
Daily risk analysis of NVDA stock using VaR, Monte Carlo simulations, and Expected Shortfall.

Objectives
Compute daily returns and descriptive statistics.
Quantify risk using VaR (historical & Monte Carlo) and Expected Shortfall.
Track rolling 60-day VaR to identify dynamic changes in risk.
Provide insights for investors and portfolio management.

Technologies / Tools
Python 3
yfinance
pandas, numpy
matplotlib

Python code
# Clone the repo
git clone [https://github.com/yourusername/nvda-risk-modeling.git](https://github.com/Elisabethu1/NVDA---Risk-Modeling-in-Python)
cd nvda-risk-modeling

# Open Jupyter Notebook
jupyter notebook NVDA - Daily Risk Modeling.ipynb

Key Findings / Insights
NVDA has moderate daily volatility (~3.1%), with rare extreme losses up to -16.97%.
Historical 95% VaR: -4.14%, Monte Carlo VaR: -4.75%, ES: -6.20%.
Rolling 60-day VaR highlights periods of elevated risk for proactive portfolio management.
Compared to Apple, NVDA has higher volatility and potential downside, making hedging and position sizing important.

Visualizations

Closing price chart (2023–2026)
Rolling 60-day VaR line chart
Histogram of daily returns with VaR & ES highlighted

Conclusion / Takeaways

NVDA is a high-growth, moderately volatile stock. VaR and ES metrics provide quantitative guidance for managing downside risk, while rolling VaR highlights periods when risk management is most critical. This analysis can support portfolio allocation and investment decisions.
