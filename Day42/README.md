# Day 42 — The Ledger: Personal Financial Command Center

Part of the [**ABTalks 60-Day Claude AI Mastery Challenge**](../README.md) — one AI-assisted build every day.

## 📖 Overview

A single-file, self-contained personal finance dashboard, purpose-built for a **freelancer with irregular, still-growing income and no debt**, whose top priority is starting to save and invest.

Rather than a generic budgeting app, it's a full command center: income logging, percent-based budgeting, an emergency-fund tracker sized in months of expenses, a goals module with an interactive SIP (compound investment) simulator, cash-flow visualization with an income-volatility score, a printable report, and a financial health score computed live from the user's own data.

No frameworks. No external libraries. No backend. Everything — including all charts — is hand-drawn on `<canvas>` in vanilla JavaScript, and all data persists locally in the browser via `localStorage`.

## ✨ Features

- 📊 **Financial Health Score** — a weighted 0–100 score across emergency fund coverage, savings rate, debt status, income diversification, and cash flow
- 💵 **Rolling-average income tracking** — built for irregular freelance payments instead of a fixed monthly salary
- 🧮 **Percent-based budgeting** — Save / Needs / Wants sliders that scale with whatever comes in, instead of a fixed ₹ budget
- 🛟 **Emergency fund tracker** — goal set in months of expense coverage, with a live progress bar
- 🎯 **Goals + SIP what-if simulator** — drag sliders for monthly investment, expected return, and duration; see a compound-growth chart update live
- 📈 **Cash flow chart** — 12-month income vs. expenses, plus an income volatility read (coefficient of variation)
- 🖨️ **Printable reports** — dedicated print stylesheet for a clean PDF export
- 🌓 **Dark / light mode**, fully responsive, keyboard-accessible
- 💾 **Persistent local storage** — no login, no server, no data leaves the browser

## 🚀 How to run

1. Download [`personal-financial-command-center.html`](./personal-financial-command-center.html)
2. Open it directly in any modern browser — that's it, no build step, no install
3. Start logging a payment or an expense; the health score and charts populate as data comes in

## 🧱 Tech stack

| Layer | Choice |
|---|---|
| Structure | Semantic HTML5 |
| Styling | Hand-written CSS (custom properties for theming, no framework) |
| Charts | Native `<canvas>` — bar/line combo chart, donut chart, SIP growth chart |
| Logic | Vanilla JavaScript (ES6+) |
| Persistence | `localStorage` |
| Fonts | Fraunces (display), Inter (body), IBM Plex Mono (numeric/data) |

## 📂 Files in this folder

| File | Purpose |
|---|---|
| `personal-financial-command-center.html` | The full working application |
| `Day42.md` | Daily build log — process, design decisions, and the bug I fixed |
| `LEARNINGS.md` | Technical and prompting lessons from today |
| `README.md` | This file |

## 🔗 Links

- 🧵 60-Day Challenge home: [`../README.md`](../README.md)
- 💻 GitHub: [sidharth0018](https://github.com/sidharth0018)
- 💼 LinkedIn: [sidharth-kumar-501768287](https://www.linkedin.com/in/sidharth-kumar-501768287)
