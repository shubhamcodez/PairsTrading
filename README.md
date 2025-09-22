## Cointegration based pairs trading strategy

Notebook link: https://colab.research.google.com/gist/shubhamcodez/be3138c72b559a06d7aa385e2ed8ed83/cointegration-based-backtest.ipynb <br>

### Overview of the project
1. OLS Regression: Conduct an Ordinary Least Squares (OLS) regression, where the first difference of the series is regressed against its value and any differences. This aims to understand the relationship between the changes in the series and its past values. 

2. Augmented Dickey-Fuller: Implement the Augmented Dickey-Fuller (ADF) test to determine the test statistic. This measures the importance of the level in explaining the changes in the series. 

3. Trading Bounds Analysis: Determine the upper and lower trading bounds from the residuals, essential for developing a pairs trading strategy.

Universe of stocks chosen: "AAPL", "MSFT", "GOOGL", "AMZN", "NVDA", "TSLA", "META", "AVGO", "AMD", "INTC", "QCOM", "MU", "SMCI", "CRCL", "MSTR", "CRWV", "NBIS", "ORCL", "PLTR", "HOOD", "COIN", "BE", "HSAI", "CRDO", "PSIX", "DAVE", "MDB", "PANW", "OKLO", "APP"

Thesis for universe construction: Trending stocks in similar sectors. Clustering analysis for verification that selected stocks experience similar volatility and returns. 
<br>
Alloted capital: 1,000,000
Allocation method: Uniform weighted across each pair selected based highest R2 relation with each other. 
<br>
### Strategy performance on a portfolio of long-short pairs
<img width="1265" height="568" alt="Cointegration Strategy - portfolio PnL" src="https://github.com/user-attachments/assets/da16c0cb-309f-4510-87bb-6c115c710d0f" />
Sharpe: 
Exploratory Analysis

<img width="978" height="463" alt="Cointegration Strategy - heirarchical cluster" src="https://github.com/user-attachments/assets/e3c8f708-be6e-439c-bafd-e30dca7665d6" />
<img width="863" height="663" alt="Cointegration Strategy - cluster" src="https://github.com/user-attachments/assets/9f706f8f-d461-4220-8b61-c0fb9bfe3847" />
<img width="1363" height="563" alt="Cointegration Strategy - rolling residual fit" src="https://github.com/user-attachments/assets/7bf57848-1b26-440a-b2d2-dd578af68609" />
