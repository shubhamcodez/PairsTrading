# Cointegration-Based Pairs Trading Strategy  

## Project Overview  
This project implements a **statistical arbitrage strategy** based on cointegration. The methodology identifies pairs of stocks with a long-term equilibrium relationship and exploits short-term deviations using a mean-reversion framework.  

### Key Steps in the Workflow  
1. **OLS Regression**  
   - Perform Ordinary Least Squares (OLS) regression where the first difference of the series is regressed against its value and lags.  
   - Helps estimate residuals that represent mean-reverting deviations.  

2. **Augmented Dickey-Fuller (ADF) Test**  
   - Conduct the ADF test on residuals to confirm stationarity.  
   - Ensures that spreads are mean-reverting and thus tradable.  

3. **Trading Bounds & Z-Score Signals**  
   - Construct residual spreads and normalize using rolling mean and standard deviation.  

4. **Portfolio Construction**  
   - **Universe:** AAPL, MSFT, GOOGL, AMZN, NVDA, TSLA, META, AVGO, AMD, INTC, QCOM, MU, SMCI, CRCL, MSTR, CRWV, NBIS, ORCL, PLTR, HOOD, COIN, BE, HSAI, CRDO, PSIX, DAVE, MDB, PANW, OKLO, APP  
   - Stocks selected based on **trending momentum** and **sector similarity**.  
   - **Clustering analysis** verifies co-movement of volatility and returns.  
   - Pairs selected using **highest R²** values.  
   - Capital = **$1,000,000**, allocated uniformly across pairs.  

---

## Exploratory Analysis  

### 1. Hierarchical Clustering Based on Correlation  
Groups stocks with similar correlation structures, aiding in pair selection.  
![Hierarchical Clustering](https://github.com/user-attachments/assets/e3c8f708-be6e-439c-bafd-e30dca7665d6)  

### 2. Clustering by Returns & Volatility  
K-means clustering of assets by mean return and volatility, verifying sector-like behavior.  
![Returns-Volatility Clustering](https://github.com/user-attachments/assets/9f706f8f-d461-4220-8b61-c0fb9bfe3847)  

### 3. Residual Z-Scores for Entry/Exit  
Z-score normalized residuals used for trade timing.  
![Residuals with Thresholds](https://github.com/shubhamcodez/PairsTrading/blob/4cd5cd96c8b4190d46d6ae7301a2da5b99a90768/results/Cointegration%20Strategy%20-%20rolling%20residual%20fit.png)  

---

## Strategy Performance  

The backtest on a **portfolio of long-short pairs** shows cumulative returns and equity curves across all trades.  

![Portfolio PnL](https://github.com/user-attachments/assets/da16c0cb-309f-4510-87bb-6c115c710d0f)  

- **Capital:** $1,000,000  
- **Weighting:** Uniform per pair
- **Returns:** 8% (33.6% annualized) 
- **Duration:** 60 days
- **Sharpe:** 5.92

---

## Methodology  

1. **Spread Calculation**  
   - Estimate spread using OLS regression of one stock against another.  

2. **Stationarity Check**  
   - Apply ADF to residuals to confirm mean-reversion property.  

3. **Signal Generation**  
   - Use rolling z-scores of residuals.  
   - Enter trades when residuals deviate significantly from equilibrium.  

4. **Risk Management**  
   - Stop-loss to cap extreme divergences.  
   - Portfolio diversification across pairs.  

---

## Next Steps  
- Expand universe to ETFs and futures.  
- Test alternative stationarity tests (Phillips-Perron, KPSS).  
- Integrate ML models for dynamic thresholding.  
- Explore optimal capital allocation using Kelly criterion and sharpe/risk weighted allocation

