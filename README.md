# Risk-Averse Portfolio Optimizer (CFM Project)

**Team Project — CFM 101, University of Waterloo**

This project implements a **risk-averse stock portfolio optimizer** using Python, essentially building a **robo-advisor portfolio** that balances risk, diversification, and returns using quantitative methods. It selects the most stable North American stocks and constructs a portfolio that minimizes risk while respecting realistic market constraints.

🏆 **Achievement:** Our project was awarded **Runner-Up (2nd Place)** in the CFM 101 Robo-Advising Challenge at the University of Waterloo.  

---

## 🏆 Project Overview

We built a **score-based ranking system** and applied **Minimum Variance Portfolio Optimization** to generate a low-risk, well-diversified portfolio:

- Filtered stocks based on **currency, liquidity, price, and trading history**.
- Calculated quantitative risk scores for each stock using:
  - **Stability (Volatility & Choppiness)**
  - **Beta (Market Sensitivity)**
  - **Average Correlation with other stocks**
  - **Market Capitalization (log-scaled)**
- Dynamically selected stocks below a **risk score threshold** while ensuring diversification:
  - **Minimum portfolio size:** 10 stocks
  - **Maximum portfolio size:** 25 stocks
  - **Sector constraints:** no more than 40% in a single sector
  - **Cap diversity:** at least one large-cap and one small-cap stock
- Optimized **portfolio weights** using Sequential Least Squares Quadratic Programming (SLSQP) to minimize variance.
- Included **transaction fees** and currency conversion to CAD.

> Result: A “risk-averse” portfolio optimized for low volatility, moderate Sharpe ratio, and controlled exposure.

---

## ⚙️ Key Features

1. **Dynamic Stock Filtering**
   - Removes delisted, illiquid, or low-price stocks
   - Validates trading volume over proper date ranges
   - Ensures high-quality, investable tickers

2. **Risk Scoring System**
   - Combines multiple factors into a **normalized score**
   - Scores used to rank stocks and select the safest subset

3. **Adaptive Portfolio Selection**
   - Uses threshold-based selection with **minimum/maximum stock limits**
   - Ensures **large-cap and small-cap inclusion**
   - Maintains **sector balance**

4. **Minimum Variance Optimization**
   - Allocates weights to minimize portfolio variance
   - Respects **weight bounds and sector constraints**
   - Calculates expected **portfolio risk, Sharpe ratio, and Beta**

5. **Backtesting**
   - Evaluates portfolio performance over multiple periods
   - Provides **daily and annualized risk metrics**
   - Simulates portfolio value under realistic market conditions

6. **Outputs**
   - **Portfolio allocation CSV** (`output.csv`)
   - **Sector allocation pie chart**
   - **Risk & performance metrics**

---

## 📈 Results

- **Sharpe Ratio:** ~1.0 (moderate risk-adjusted performance)
- **Standard Deviation:** Low annualized risk
- **Variance:** Minimal, stable portfolio
- **Transaction Fees:** Optimized for minimal cost
- **Budget Allocation:** CAD 1,000,000 correctly allocated among selected stocks
- **Beta:** Low portfolio sensitivity to market

The portfolio demonstrates **risk minimization, diversification, and realistic investment constraints**.

---

## 🛠 How to Run

1. Install dependencies:

```bash
pip install pandas numpy yfinance matplotlib scipy


## How to Run

1. Install dependencies:

    ```bash
    pip install pandas numpy yfinance matplotlib scipy
    ```

2. Place `Tickers.csv` in the project directory.

3. Run the main script:

    ```bash
    python main.py
    ```

4. After running, the following will be generated in the project folder:
   - `output.csv` — your final portfolio with tickers, weights, and CAD allocation.
   - Sector breakdown and portfolio performance charts.



