# Tradebook

A trading journal that runs in the browser. Log trades, import your MetaTrader 5 history as CSV, and track your performance over time. No build step and no dependencies.

## Project structure
```
tradebook/
  index.html      page structure
  css/style.css   all styling (brand palette, light and dark themes)
  js/app.js       data, stats, charts, CSV import, forms
  js/features.js  accounts, currency, screenshots, checklist, drawdown, backup
  js/cloud.js     optional Supabase login and sync
  js/news.js      live market headlines
  js/bank.js      bank-style balance card and recent activity
  js/ui.js        navigation, slide-in trade form, filters toggle, theme, shortcuts
  supabase/schema.sql  database table for cloud sync
  README.md
  .gitignore
```

## Features
- Bank-style balance card with animated balance, hide balance (key B), today and monthly change, return, quick actions and a recent activity statement
- Five views: Dashboard, Journal, Calendar and Tools
- Slide-in trade form from the floating button (keyboard shortcut: N)
- Filters by symbol, side, setup and date range that update every stat, chart and table
- Equity curve, win rate, profit factor, reward to risk, expectancy, drawdown, average R, best and worst trade, streaks
- Results by symbol, setup, weekday, side or mood
- Setup tags, notes and mood on every trade, plus edit and delete
- Monthly calendar with a profit target and daily loss limit
- MT5 CSV import (duplicates skipped) and position size calculator
- Multiple accounts, each with its own currency (dollar, euro, pound, naira)
- Chart screenshot and pre-trade checklist on every trade, with results by checklist score
- Drawdown chart
- Backup and restore as a JSON file
- Live market news (FXStreet, CNBC, BBC, BusinessDay) with keyword filter
- Optional cloud sync and login with Supabase
- Light and dark mode, mobile friendly, data saved in the browser (localStorage)

## Run it
Open `index.html` in any browser.

## Deploy with GitHub Pages
1. Push this repo to GitHub.
2. Settings > Pages > source: `main` branch, root folder.
3. Your site goes live at `https://<your-username>.github.io/<repo-name>/`.

## Cloud sync setup (optional)
1. Create a free project at supabase.com.
2. Open SQL Editor, paste `supabase/schema.sql`, and run it.
3. In Project Settings > API, copy the Project URL and the anon public key.
4. In Tradebook, open Tools > Cloud sync, paste both, create an account, sign in, and press Sync now.

Use the anon key only. The security rules in the schema make sure each user can read and write only their own journal. Sync merges trades from all your devices. Screenshots are included, so a journal with many images can get large.

## Notes
- Live news comes through the free rss2json.com service, which has usage limits. If a feed does not load, press Refresh or open the source site.
- Pip value in the position size calculator varies by symbol and broker.

## Roadmap
- Per-trade tags search
- Import from more brokers
