# Day 31/60 — AI Supply Chain Control Tower 🎮⚙️

> Part of the **60-Day Claude AI Mastery Challenge** — building one AI-assisted project every day for 60 days, toward a Data Analyst / Data Science role.

## 🧠 What This Is

A single-file, fully offline **decision-making simulation game** that puts the player in the seat of a **Head of Operations** managing a global supply chain network under live pressure.

Third build in this week's supply chain arc:
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
6. Alert frequency ramps up as the clock runs down.
7. At time's up: final Score, KPI snapshot, and a letter grade (A+ → D) with a performance summary.

## 📊 KPIs Tracked

| KPI | Behavior |
|---|---|
| Service Level % | Higher is better |
| Customer Satisfaction | Higher is better |
| Inventory Health | Higher is better |
| Transportation Efficiency | Higher is better |
| Operating Cost | Lower is better (cost index) |
| Revenue Protected | Higher is better |
| Score | Cumulative decision quality |

## 🛠️ Tech Stack

Pure HTML + CSS + Vanilla JavaScript — zero frameworks, zero CDN calls, zero backend. Deliberate choice this time: **no React**, unlike Day 30, whose build broke offline because it depended on CDN-hosted React/Babel that silently fail with no network. Kept the entire game state in one plain JS object with modular functions (`spawnAlert`, `resolveAlert`, `applyEffects`, `tick`, `endGame`) instead of components — a hand-rolled reducer pattern that sidesteps the exact bug class that blocked Day 30.

## ✨ Features

- Animated glowing KPI cards with live color-coded health bars
- Priority-coded alert cards (critical/medium/low) with pulse animation on critical alerts
- Countdown timers per-alert and for the overall shift
- Live scrolling event log with color-coded outcomes
- Pause / Resume, sound toggle (visual-only), Help modal
- End-of-shift grading engine (Score + average KPI health → A+ to D)
- Fully responsive for desktop and mobile

## 🔑 Key Learnings

- **Architecture as bug prevention**: turned Day 30's unresolved CDN-failure bug into an explicit Day 31 decision — vanilla JS by default for any offline single-file deliverable, React only when component reuse earns its complexity.
- **State machine over component tree**: one `state` object + pure functions is essentially a hand-rolled reducer — same mental model as `useReducer`/Redux, without the framework overhead.
- **Recursive `setTimeout` for a changing tick rate**: used self-rescheduling timeouts (not `setInterval`) to ramp alert-spawn frequency dynamically as the game progresses — `setInterval` can't change its own delay without being torn down and recreated.
- **Guarding delayed callbacks**: every `setTimeout`-based delayed consequence checks `if(!state.running) return` first, to prevent a stale timeout from a finished game corrupting the state of a new one after "Play Again."
- **Modeling asymmetric KPIs**: Operating Cost is the one metric where lower = better; handled with an `invert` flag in KPI metadata rather than hardcoding exceptions throughout the render logic.

## 📁 Files

- `index.html` — the complete game, open directly in a browser
- `day31.md` — this file

---
*Day 31 of 60 — building toward a Data Analyst / Data Science role, one project at a time.*
