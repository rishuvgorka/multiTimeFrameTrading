
# 📈 Multi-TimeFrame Trading Strategy

This repository implements a complete multi-timeframe trading strategy in Python, allowing for both backtesting and live trading using Binance Testnet. The code is modular and built for ease of extension and replication of backtest conditions during live deployment.

---

## 🧠 Strategy Overview

- **Entry Timeframe**: 15 minutes  
- **Confirmation Timeframe**: 1 hour  
- **Indicators Used**:
  - SMA / EMA Pullback Strategy
  - RSI for confirmation
- **Execution Logic**:
  - Wait for confirmation on higher timeframe
  - Execute on lower timeframe only when conditions match
  - SL/TP logic incorporated
  - Trade logging and CSV export

---

## 📁 Folder Structure

```text
multiTimeFrameTrading/
├── config.py                 # Configuration variables (API_KEY, API_SECRET)
├── backtest.py               # Backtesting the strategy using historical data
├── fetchData.py              # Fetch and prepare OHLCV data
├── strategy.py               # Strategy class with signal logic
├── MultiTimeFrameStrategy.html  # HTML report/output
├── log.txt                   # optional file when you run live_trading in the background
├── live_trading.py          # Live trading logic for Binance Testnet
├── .gitignore
├── binance_client.py        # Binance API client setup
├── comparison.py            # compare the trade results by both backtest and live-trading
├── inFiles/                 # Store the OHLCV data for 15min and 1h
└── ouFiles/                 # Store the trade log for backtest and live trading
     ├── backtestTrades.csv  # Trade log for backtesting
     ├── live_trades.csv     # Trade log for live trading
     └── position.csv        # tracks the current or historical positions
```

---

## 🚀 Usage

### 1. 📦 Install Requirements
Make sure to install required packages:

```bash
pip install pandas backtesting python-binance requests
```

### 2. ⚙️ Configure
Edit `config.py` to set:
- API_KEY
- API_SECRET 

### 3. 🧪 Run Backtest

```bash
python backtest.py
```

Stats will be printed, whereas trade log will be saved as csv file in ouFiles.

### 4. 🟢 Run Live Trading (Binance Testnet)

Make sure your Binance Testnet API keys are correctly set in `binance_client.py`, then:

```bash
python live_trading.py
```

Trades will be saved in ouFiles as live_trades.csv.

---

## 📊 Output

- Trade logs for both backtest and live trading as csv file
- A .html file which shows the trades done by backtest

---
