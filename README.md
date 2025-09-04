# Simple RSI D1 Cross Screener (≥$1B MC)

Fixed filters:
- Timeframe: D1 (daily)
- Market cap: ≥ $1,000,000,000 (from CoinGecko)
- RSI: 14, source = close, calculated on D1 (Wilder)
- Crosses: any cross of 30, 50, or 70 within the last 4 closed days

What it does:
- Fetches top market-cap coins from CoinGecko, filters to ≥ $1B.
- Intersects with Binance USDT‑M PERPETUAL symbols.
- Downloads daily klines from Binance Futures, computes RSI(14).
- Detects crosses of 30/50/70 in the last 4 closed candles and lists them.

How to use:
1. Create a new GitHub repo and add the files in `docs/` (this `index.html`).
2. Enable GitHub Pages: Settings → Pages → Build and deployment → Source: "Deploy from a branch", Branch: `main` and Folder: `/docs`.
3. Open your Pages URL and click “Scan now”.

Notes:
- TradingView links open at BINANCE: `BASEUSDT.P` (perpetuals).
- Binance links open USDT-M futures symbol.
- Cross detection uses the last 4 closed D1 candles, not the current forming candle.
- Coin/Exchange symbol mismatches may exclude some assets even if MC ≥ $1B.

Troubleshooting:
- If no results: it’s normal depending on market conditions (few recent crosses).
- Rate limits: the app rate-limits requests, but if you see API errors, wait 1–2 minutes and scan again.
- Local testing: open `docs/index.html` with a simple HTTP server (avoid `file://` in some browsers).
