# LEARNINGS — Day 31: AI Supply Chain Control Tower

## 🎯 What I Set Out to Build
A timed, game-ified simulation of real-time supply chain crisis management — different from Day 29's diagnostic lab and Day 30's builder tool, this one is about **reacting under pressure with incomplete time**, closer to how ops dashboards actually feel during a live disruption.

## 🔑 Key Technical Learnings

### 1. Avoiding Day 30's CDN failure by design
Day 30's Supply Chain Builder went blank offline because it depended on CDN-hosted React + Babel, which silently fail with no network. Rather than just patching that build, I made an explicit architectural call for Day 31: **plain vanilla JS, zero external dependencies of any kind.** No CDN, no build step, no risk surface. This is now my default for any "must work fully offline, single-file" deliverable going forward — React/JSX is only worth reaching for when component reuse genuinely earns its complexity.

### 2. State machine over component tree
Instead of components + props + state hooks, I modeled the whole game as one `state` object with pure functions acting on it: `spawnAlert()`, `resolveAlert()`, `applyEffects()`, `tick()`, `expireAlert()`, `endGame()`. Rendering functions (`renderKPIGrid`, `renderAlerts`) just redraw from `state` on every change. This is basically a tiny reducer pattern without a framework — useful to recognize since it's the same mental model as Redux/useReducer, just hand-rolled.

### 3. Designing "delayed consequences" without async complexity
Used plain `setTimeout` calls scoped inside `resolveAlert()` to simulate real-world lag between an operational decision and its downstream effect. Had to guard every delayed callback with `if(!state.running) return` so a stale timeout firing after game-end (or a Play Again reset) doesn't corrupt the new game's state — an easy bug to miss with setTimeout-heavy game loops.

### 4. Difficulty ramp via a self-rescheduling timer
Rather than `setInterval` at a fixed rate for spawning alerts, I used a recursive `setTimeout` (`scheduleNextSpawn`) that recalculates its own delay every time based on elapsed-time ratio. This is the cleaner pattern whenever a "tick rate" needs to change dynamically mid-game — `setInterval` can't have its delay changed without clearing and recreating it anyway, so recursive `setTimeout` is less error-prone here.

### 5. KPI system design: mixing "higher is better" and "lower is better" metrics
Operating Cost is the one KPI where lower = better, unlike the other five. Handled this with an `invert` flag in the KPI metadata array so the color-coding and bar-fill logic could branch cleanly instead of special-casing it inline everywhere. Small thing, but a good reminder to model asymmetric metrics explicitly rather than hardcoding exceptions.

## 🧩 Product/Design Learnings

- **Three cognitive modes, one domain**: Crisis Lab (diagnose) → Builder (design) → Control Tower (react-in-real-time) — reusing a domain across different *interaction modes* is a strong way to keep producing fresh challenge-day content without the domain research overhead of starting from scratch each day.
- **Grading transparency matters**: the end-of-shift grade formula (Score threshold + average KPI health threshold, not score alone) prevents a player from "gaming" a good grade by spamming low-effort actions — a small balance decision but one that mirrors real performance-review design (you don't get an A for hitting one metric while others collapse).

## 🔜 Next Steps / Skill Gaps Reinforced
- Continues building muscle memory in vanilla JS state management, which is transferable to no-framework dashboard work in interviews and take-home tests.
- Reinforces the offline-single-file constraint as a genuinely useful discipline — good prep for any Data Analyst/Data Science take-home that says "no internet access allowed in sandbox," which several recruiters have flagged as a real constraint.
- Still on the roadmap: Power BI, DAX, and advanced Excel — none of these directly used today, but the KPI-thresholding and grading logic here is conceptually the same as building calculated measures in DAX, just in JS instead.

---
*Day 31 of 60 — [ABTalks Claude AI Mastery Challenge](https://github.com/sidharth0018)*
