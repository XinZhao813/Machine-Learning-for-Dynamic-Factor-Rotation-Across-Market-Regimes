# Machine Learning Factor Rotation Across Market Regimes

## Overview

This project investigates whether machine learning models can extract predictive signals from macroeconomic variables and improve systematic factor allocation.

The project combines Fama-French six-factor models, macroeconomic predictors, and machine learning techniques to evaluate factor return predictability and construct a dynamic factor rotation strategy across different market regimes.

---

## Methodology

### Factor Return Prediction

Six Fama-French factors were analyzed:

- Market Risk Premium (MKT)
- Size (SMB)
- Value (HML)
- Profitability (RMW)
- Investment (CMA)
- Momentum (MOM)

Machine learning models were trained to predict future monthly factor returns using macroeconomic predictors, including valuation ratios, interest rates, and market indicators.

Models implemented:

- LASSO Regression
- Random Forest
- Neural Network

---

### Rolling Window Framework

To avoid look-ahead bias, a rolling window approach was used for out-of-sample prediction.

At each month, models were trained using the previous 60 months of historical data and then used to predict the following month's factor returns.

This process was repeated through the entire sample period, creating a realistic investment environment where only information available at the time was used.

---

### Market Regime Classification

Market conditions were classified using the CBOE Volatility Index (VIX).

Two market regimes were considered:

- Low-volatility regime
- High-volatility regime

Model performance and portfolio returns were evaluated separately across different regimes to examine whether factor predictability changes under different market conditions.

---

### Portfolio Construction & Backtesting

A long-short factor rotation strategy was constructed by:

- Going long the factor with the highest predicted return
- Shorting the factor with the lowest predicted return

Strategy performance was evaluated using:

- Sharpe Ratio
- Hit Ratio
- Out-of-Sample R²
- Cumulative Returns

---

## Results

Key findings:

- Machine learning models generated meaningful factor rotation signals despite limited return prediction accuracy.
- Strategy performance was strongly regime-dependent.
- Annualized Sharpe Ratios reached approximately **0.70–0.78 during low-volatility periods**.

---

## Technologies

R | Machine Learning | Statistical Modeling | Portfolio Backtesting

Libraries:
- glmnet
- randomForest
- nnet
- tidyverse
- quantmod
