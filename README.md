# Investment Simulator 📈

A fictional portfolio simulator that lets you track investments and backtest hypothetical scenarios using real market data.

**Live:** https://brauliopastran.github.io/inversion-simulator/

## Features

- **📊 Portfolio Tracking** — Record your stock purchases and track performance in real-time
- **🔮 Hypothetical Backtesting** — See what you would have earned if you'd invested in any stock at any date (up to 15 years ago)
- **📈 Real Market Data** — Powered by Yahoo Finance, updated every 15 minutes via GitHub Actions
- **💾 Efficient Storage** — Stores weekly prices for the last year + monthly prices for older data (not daily — keeps file size manageable)

## How It Works

1. Stock prices are fetched from Yahoo Finance every 15 minutes by GitHub Actions and stored in `data/prices.json`
2. Historical data is stored with smart granularity: weekly (last 1 year) + monthly (up to 15 years)
3. The web app loads data directly from GitHub Pages — no server, no backend needed
4. Portfolio is managed in-browser (localStorage) — add, edit, or delete purchases directly from the web

## Project Structure

```
inversion-simulator/
├── index.html                    # Main web app (single file, no build)
├── data/
│   ├── portfolio.json            # Your purchases (managed from the web)
│   └── prices.json               # Current + historical prices (auto-updated)
├── scripts/
│   └── fetch-prices.js           # Node.js script run by GitHub Actions
├── .github/workflows/
│   └── fetch-prices.yml          # GitHub Actions workflow
└── README.md                     # This file
```

## Supported Tickers

VOO, VTI, SPY, QQQ, AAPL, MSFT, CCJ, NEE, VEA, VT

## Data Sources

- Real-time and historical prices: [Yahoo Finance API](https://finance.yahoo.com/)
- Hosted on: [GitHub Pages](https://pages.github.com/)
- Data updates: [GitHub Actions](https://github.com/features/actions)

## Hypothetical Simulator

Select any ticker, date, and amount to see what your investment would be worth today. Perfect for learning about long-term investing without risking real money.

> ⚠️ This is a simulation tool for educational purposes only. Not financial advice.

## Tech Stack

- Vanilla HTML/CSS/JavaScript (no framework)
- [Chart.js](https://www.chartjs.org/) for charts
- Yahoo Finance API for market data
- GitHub Actions + GitHub Pages for hosting and automation
- Browser localStorage for portfolio persistence

## License

MIT