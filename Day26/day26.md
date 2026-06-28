# Day 26 — Prior Authorization Workflow Simulator

**60-Day Claude AI Mastery Challenge | ABTalks**

An interactive, gamified, drag-and-drop simulation of the US healthcare **Prior Authorization (PA)** process — built as a single self-contained HTML file with zero dependencies.

🔗 **Live demo:** open `pa_simulator.html` directly in any browser (no server, no install).

---

## 🎯 What this project does

Prior Authorization is one of the most friction-heavy workflows in US healthcare — a request for a medical service has to pass through the **Patient**, **Provider**, and **Payer** before care can proceed. This simulator turns that real-world process into an interactive board game so the mechanics (and the pain points) become intuitive.

The user drags a single "case card" across three lanes — **Patient → Provider → Payer** — through 7 stages:

1. Care Requested
2. Medical Necessity Evaluation
3. Document Collection
4. Submission to Payer
5. Payer Review
6. Outcome (Approved / Pended / Denied)
7. Resolution — including Peer-to-Peer Review and Formal Appeal paths for denials

Every action triggers a short, plain-language educational explanation describing what's happening in the real-world process at that step.

## 🧩 Key features

- **3 drag-and-drop lanes** (Patient / Provider / Payer) with native HTML5 drag events
- **4 patient scenarios** stored in an editable JS array: elective surgery, MRI, specialty medication, inpatient admission
- **Document checklist** per scenario — incomplete documentation lowers approval odds, mirroring real payer behavior
- **Weighted decision engine** — approval/pend/denial probability is computed from a "medical necessity strength" score, document completeness, and prior pend count
- **Denial recovery paths** — Peer-to-Peer Review and Formal Appeal, each with a random chance to overturn the decision
- **Live stats bar** — Days Elapsed counter and an Efficiency Score that drops with pends, denials, and missing documents
- **Confetti celebration** animation on approval (pure CSS/JS, no libraries)
- **End-of-case summary modal** with a full event timeline, final stats, and a "Start New Patient" restart flow
- **Progress tracker** across the top showing all 7 stages with active/completed states

## 🛠️ Tech stack

- **HTML + CSS + Vanilla JavaScript only** — no frameworks, no CDNs, no build step
- **No localStorage / cookies** — all state lives in JS memory for the session (per the project's deliberate constraint)
- Single file: `pa_simulator.html` — fully portable, runs offline

## 🤖 How Claude was used

This was built through an iterative, conversational prompt → build → test → fix loop with Claude:

1. Gave Claude a detailed functional spec (lanes, stages, scenarios, outcomes, UI constraints)
2. Claude generated the complete single-file HTML app in one pass, including a state machine for stage progression and a probability-weighted payer decision engine
3. Manually tested the drag-and-drop flow in-browser and shared screenshots back to Claude at each stage
4. Claude diagnosed a real logic bug from a screenshot alone (a same-lane drag-and-drop was being silently blocked) and shipped a fix in the same file without breaking existing state

See `LEARNINGS.md` for the detailed breakdown of what worked, what broke, and what I'd do differently.

## 📂 Files in this folder

| File | Description |
|---|---|
| `pa_simulator.html` | The complete, runnable simulator (open directly in a browser) |
| `README.md` | This file |
| `LEARNINGS.md` | Day 26 reflections — prompting approach, bugs found, and key takeaways |

## 🚀 How to run

1. Download `pa_simulator.html`
2. Double-click it (or drag into any browser window)
3. Pick a patient scenario and start dragging the case card through the lanes

No installation, no internet connection, no dependencies required.

---

**Part of my [60-Day Claude AI Mastery Challenge](https://github.com/sidharth0018) — one AI-assisted build, every day, fully documented.**
