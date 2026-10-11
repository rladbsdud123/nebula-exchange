# Nebula Exchange

A fictional cryptocurrency exchange trading terminal, built from scratch as a front-end portfolio piece. It uses **real live market data** for prices while keeping all accounts, balances, and orders simulated — so it looks and behaves like a real exchange without being one.

**🔗 Live demo:** https://<your-username>.github.io/nebula-exchange/

> Replace `<your-username>` above with your GitHub username (find it under your profile menu on github.com). If you deploy on Vercel or Netlify instead, put that URL here.

![Nebula Exchange screenshot](screenshot.png)

> Add a `screenshot.png` to the repo root so this preview shows up. A quick screen capture of the trading view (dark mode looks best) works well.

---

## What it does

- **Live price feed** — real-time quotes for BTC, ETH, SOL, XRP, ADA, and DOGE pulled from the CoinGecko public API. No API key required.
- **Interactive price chart** — 24-hour price history drawn as a hand-built SVG line + area chart, with a live last-price marker.
- **Order book** — bid/ask ladder with cumulative-depth bars, generated around the real mid price.
- **Trade panel** — Buy/Sell tabs, Limit / Market / Stop order types, an amount slider, and live order-value + fee calculation.
- **Wallet / portfolio** — holdings valued at real market prices, with a one-click **USD ↔ KRW (원화)** toggle using a live exchange rate.
- **My Orders** — placed orders are recorded in a live-updating history table.
- **Demo login** — a local sign-in gate (credentials stored only in the browser) that shows a full auth flow.
- **Light / dark themes** — follows the system theme with a manual toggle, and is fully responsive down to phone width.

## Tech

- **No framework, no build step** — plain HTML, CSS, and vanilla JavaScript in a single file.
- **CoinGecko REST API** for real market data (polled on an interval).
- **SVG**, drawn in code, for the price chart and sparklines.
- **CSS custom properties** for theming (light/dark via `prefers-color-scheme` + a manual override).
- **`localStorage`** for the demo session.

## Running locally

No install or build needed — just open the file in a browser:

```
# option 1: double-click index.html

# option 2: serve it (needed by some browsers for fetch to work smoothly)
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploying

This is a static site, so any static host works:

- **GitHub Pages** — Settings → Pages → Deploy from branch → `main` / root.
- **Vercel** or **Netlify** — connect the repo and deploy; redeploys happen automatically on every push.

Make sure the file is named `index.html` so it loads at the site root.

## Notes & limitations

- Prices are **real**; accounts, balances, order matching, and the order book depth are **simulated** for demonstration.
- CoinGecko's free tier is rate-limited. If requests are throttled, the status indicator shows *offline — retrying* and recovers on the next cycle.
- This is a learning / portfolio project and **not** a real exchange. It handles no real assets and takes no real money.

## License

MIT — feel free to learn from it or build on it.
