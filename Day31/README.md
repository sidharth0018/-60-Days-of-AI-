# Day 31/60 — AI Supply Chain Control Tower 🎮⚙️

> Part of the **[ABTalks 60-Day Claude AI Mastery Challenge](https://github.com/sidharth0018)** — building one AI-assisted project every day for 60 days.

## 🧠 What This Is

A single-file, fully offline **decision-making simulation game** that puts the player in the seat of a **Head of Operations** managing a global supply chain network under live pressure.

It's the third build in my supply chain arc this week:
- **Day 28** → Hospital Admission Readiness Simulator (healthcare RCM)
- **Day 29** → Supply Chain Crisis Lab (diagnose-the-disruption)
- **Day 30** → Supply Chain Builder (design-your-own-network)
- **Day 31 (this one)** → Supply Chain **Control Tower** (react-in-real-time, under a clock)

Same domain, three different cognitive modes: **diagnose → design → react**.

## 🚀 Live Demo

Open `index.html` directly in any browser — no server, no build step, no internet connection required after download.

## 🎯 Core Gameplay Loop

1. A 3-minute shift begins.
2. Random operational alerts spawn (Port Congestion, Supplier Delay, Truck Breakdown, Demand Spike, etc.), each with a countdown.
3. Player picks one of several response actions per alert.
4. Every action shifts 6 live KPIs — some help immediately, some help but cost more, some (ignoring) actively hurt.
5. A few actions have **delayed consequences** that land 4–7 seconds later — mirroring how real ops decisions don't show their full cost/benefit instantly.
6. Alert frequency ramps up as the clock runs down (more alerts, shorter fuses).
7. At time's up: final Score, KPI snapshot, and a letter grade (A+ → D) with a short performance summary.

## 📊 KPIs Tracked

| KPI | Behavior |
|---|---|
| Service Level % | Higher is better |
| Customer Satisfaction | Higher is better |
| Inventory Health | Higher is better |
| Transportation Efficiency | Higher is better |
| Operating Cost | **Lower is better** (cost index) |
| Revenue Protected | Higher is better |
| Score | Cumulative decision quality |

## 🛠️ Tech Stack

- **Pure HTML + CSS + Vanilla JavaScript** — zero frameworks, zero CDN calls, zero backend
- Single self-contained `.html` file — works fully offline, unlike Day 30's build which broke due to CDN-dependent React/Babel not resolving offline
- Deliberate architecture choice this time: **no React** — kept the state machine in a plain JS object (`state`) with modular functions (`spawnAlert`, `resolveAlert`, `applyEffects`, `tick`, `endGame`) instead of components, to sidestep the exact class of bug that blocked Day 30

## ✨ Features

- Animated glowing KPI cards with live color-coded health bars (green/orange/red)
- Priority-coded alert cards (critical/medium/low) with pulse animation on critical alerts
- Countdown timers per-alert and for the overall shift
- Live scrolling event log with color-coded outcomes
- Pause / Resume
- Sound toggle (visual-only, per spec — no audio assets)
- Help/Instructions modal
- End-of-shift grading engine (Score + average KPI health → A+ to D)
- Fully responsive for desktop and mobile

## 📁 Files

```
Day31-AI-Supply-Chain-Control-Tower/
├── index.html      # The complete game — open this in a browser
├── README.md        # This file
└── LEARNINGS.md      # What I learned building this
```

## 🔗 Connect

- GitHub: [github.com/sidharth0018](https://github.com/sidharth0018)
- LinkedIn: ABTalks 60-Day Claude AI Mastery Challenge

---
*Building toward a Data Analyst / Data Science role — this challenge is my daily proof-of-work.*
