# Stat Arb Lab

A hands-on learning journey into **statistical arbitrage** with Python, from first principles to an automated paper-trading pairs strategy.

All code in this repository is written by me as I learn. Each stage has a notebook (exploration and explanation) and reusable code in `src/statarb/`.

> ⚠️ Educational project. Nothing here is financial advice. Strategies are tested on historical data and paper accounts only.

---

## Repository structure

```
stat-arb-lab/
├── README.md              # this file: roadmap, journal, results
├── requirements.txt
├── notebooks/             # one notebook per stage
├── src/statarb/           # reusable code (data, pairs, signals, backtest)
├── tests/                 # unit tests for src/
├── research/              # findings and "what didn't work" write-ups
└── data/                  # cached data (git-ignored)
```

---

## Roadmap

### Stage 0: Foundations
**Concepts**
- [ ] Prices vs simple returns vs log returns (and why log returns add up over time)
- [ ] Stationarity: what it is and why most price series don't have it
- [ ] Refresher: OLS regression and hypothesis testing in Python (`statsmodels`)

**Build**
- [ ] `src/statarb/data.py`: download daily prices (`yfinance`) and cache them to disk
- [ ] Notebook `00_foundations.ipynb`: plot prices vs returns and test both for stationarity

### Stage 1: Finding relationships
**Concepts**
- [ ] Correlation vs cointegration: why high correlation is not enough
- [ ] Augmented Dickey-Fuller (ADF) test
- [ ] Engle-Granger two-step method

**Build**
- [ ] `src/statarb/pairs.py`: `find_pairs()` scanner over a universe of tickers
- [ ] Notebook `01_cointegration.ipynb`

### Stage 2: The spread
**Concepts**
- [ ] Hedge ratio: static OLS → rolling OLS → Kalman filter
- [ ] Z-score of the spread
- [ ] Ornstein-Uhlenbeck process and the half-life of mean reversion

**Build**
- [ ] `src/statarb/signals.py`: spread, z-score, half-life
- [ ] Notebook `02_spread.ipynb`

### Stage 3: Backtesting
**Concepts**
- [ ] Entry and exit rules, stop-losses
- [ ] Transaction costs and slippage
- [ ] Look-ahead bias and survivorship bias
- [ ] Metrics: Sharpe ratio, max drawdown, turnover

**Build**
- [ ] `src/statarb/backtest.py`: vectorized backtester
- [ ] Notebook `03_backtest.ipynb`

### Stage 4: Honest evaluation
**Concepts**
- [ ] Multiple-testing bias (scanning thousands of pairs!)
- [ ] In-sample vs out-of-sample, walk-forward validation
- [ ] Parameter sensitivity and overfitting

**Build**
- [ ] Research loop: formation period → trading period, rolled through time
- [ ] Notebook `04_validation.ipynb`

### Stage 5: Beyond pairs
- [ ] Johansen test for baskets of 3+ assets
- [ ] PCA residual mean reversion
- [ ] ETF vs its constituents

### Stage 6: Automation
- [ ] Paper trading account (e.g. Alpaca / IBKR paper)
- [ ] Scheduled daily signal generation and order placement
- [ ] Logging and monitoring

---

## Learning journal

| Date | Stage | What I learned | Open questions |
|------|-------|----------------|----------------|
|      |       |                |                |

## What didn't work (and why)

_Failed ideas are worth recording. Add them here._

## Results

_To be filled in from Stage 3 onwards._
