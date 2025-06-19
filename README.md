# High Volume Day Strategy (Pine Script for TradingView)

This is a Pine Script indicator designed for TradingView that detects breakout trading setups based on pre-market consolidation and price action.

## 📂 Project Structure

high-volume-day-strategy/
├── high-volume-day-strategy.pine
├── README.md
├── LICENSE
└── .gitignore

## 🚀 Features

- Identifies **pre-market high and low** (based on candle bodies)
- Detects **breakouts** during regular trading hours
- Draws **5% price target** above breakout
- Optional **1:3 Risk:Reward** visualization
- Configurable for 1-minute charts with extended hours enabled

## 📈 Strategy Overview

This indicator supports traders using a breakout pattern strategy with the following logic:
- Pre-market defined as 04:00–09:30 ET
- Uses body-based high/low detection
- Flags breakouts above pre-market high after open
- Designed to assist in decision-making, not automate trades

## 🛠 How to Use

1. Open TradingView and use a **1-minute chart** with **extended hours enabled**
2. Apply the script by copying `high-volume-day-strategy.pine` into the Pine Editor
3. Click **Add to Chart**
4. Watch for breakout signals after 9:30am ET

## 📦 Installation (via GitHub)

```bash
git clone https://github.com/your-username/high-volume-day-strategy.git
```

## 🤝 Contributing

This is an early MVP — PRs welcome to improve pattern detection or parameter configurability.
