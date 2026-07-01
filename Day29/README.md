# Day 29 — Operation Lifeline: Supply Chain Crisis Lab

**#60DayClaudeChallenge | Day 29/60**

An interactive, single-file supply chain crisis simulator built entirely with React (CDN) + Babel JSX, no backend, no build tools, no dependencies beyond two CDN scripts. Open the HTML file and it runs — fully offline after first load.

🔗 **Live file:** `Operation-Lifeline-Supply-Chain-Crisis-Lab.html` (open directly in any browser)

---

## 🎯 What This Project Does

You take over a randomly generated fictional company and live through a randomly generated supply chain crisis — a factory fire, a port strike, a cyberattack, a supplier bankruptcy — and make five stages of decisions that a real Supply Chain / Operations leader would face:

1. **Company Generation** – random industry, revenue, factories, warehouses, suppliers, inventory days, lead time, sourcing countries
2. **Crisis Generation** – one of eight real-world disruption types, each with urgency level and business impact
3. **War Room** – choose 3 of 6 response actions; each one trades off Cost, Inventory, Profit, Delivery Speed, and Customer Satisfaction
4. **Supplier Negotiation** – 4-round branching negotiation affecting Trust, Price, and Lead Time
5. **CEO Boardroom** – 5 leadership questions scored on decision quality
6. **AI Strategy** – choose 2 of 5 AI investments (Demand Forecasting, Inventory Optimization, Supplier Risk Monitoring, Warehouse Vision, Procurement Copilot)
7. **Final Dashboard** – composite 0–100 Overall Crisis Score broken into Leadership, Negotiation, Resilience, Cost Control, Risk Management, and Customer Satisfaction, plus personalized feedback: best decision, biggest mistake, expert recommendation, lessons learned

Every playthrough is fully randomized — different company, different crisis, different outcomes — so it replays well and no two sessions look the same.

---

## 🧠 Why I Built This

I wanted a project that combined three things I'm actively building toward for Data Analyst / Data Science roles:

- **Decision-consequence modeling** — every choice maps to a weighted effect on multiple KPIs simultaneously, which is the same logic behind scoring engines, credit models, and risk dashboards
- **Domain fluency in supply chain/ops** — a recurring theme across Days 25–29 of this challenge, since supply chain and RCM-style operational domains show up often in analyst JDs at product companies
- **Beginner-first UX design** — every screen explains *why* a decision matters before the user commits to it, not just what the options are

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| UI Framework | React 18 (CDN, no npm) |
| JSX Compilation | Babel Standalone (in-browser) |
| Styling | Plain CSS (custom dark enterprise theme, CSS variables) |
| State Management | React `useState` (no Redux/Context needed) |
| Data | Fully client-side, randomized in-memory — no backend, no API |
| Deployment | Single `.html` file — works fully offline |

**No Tailwind. No build step. No external assets. One file, zero setup.**

---

## 🎨 Design Decisions

- **Premium dark theme** inspired by enterprise dashboards (Stripe/Linear-style dark UI) — gradient title text, glassy cards, soft glows on hover
- **Progress dots** at the top of every stage so the user always knows where they are in the 6-step flow
- **Animated progress bars** for every KPI so consequences feel visible, not just numeric
- **"Why does this matter" callouts** on every decision point — this was the single most important UX requirement, since the goal was to make a complete beginner feel smart, not lost
- **Composite scoring model** in the final dashboard — a weighted formula across 6 sub-scores rolls up into one Overall Crisis Score, similar to how a real KPI scorecard or credit risk score is constructed

---

## 📂 Files in This Folder

```
Day29-Operation-Lifeline-Supply-Chain-Crisis-Lab/
├── Operation-Lifeline-Supply-Chain-Crisis-Lab.html   ← the full app (open this in a browser)
├── README.md                                          ← this file
└── LEARNINGS.md                                       ← reflections, prompting approach, what I'd improve
```

---

## 🚀 How to Run

1. Download `Operation-Lifeline-Supply-Chain-Crisis-Lab.html`
2. Double-click to open in Chrome/Edge/Firefox
3. No install, no server, no internet required after the first load (React/Babel load once from CDN and are cached by the browser)

---

## 🔗 Part of the 60-Day Claude AI Mastery Challenge

Every day I build and publicly document one AI-assisted project — code pushed to GitHub, reflections posted on LinkedIn. This is Day 29.

**Previous days in this repo:** Day 25 (AI Shark Tank Simulator), Day 21 (Digital Footprint Privacy Dashboard), Day 20 (Webcam Face Puzzle Game), Day 19 (Football Intelligence Hub), Day 18 (Brain-Dump Action Planner), Day 16–17 (Stock Fundamental Research + Fuel Analytics Dashboard)

📌 Follow the full challenge: [github.com/sidharth0018](https://github.com/sidharth0018)
