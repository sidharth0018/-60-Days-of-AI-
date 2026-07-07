# Day 37 — Task Compass (Café/Restaurant Edition)

**ABTalks 60-Day Claude AI Mastery Challenge**

An interactive, offline-first management simulation that teaches how work actually flows through an organization — ownership, delegation, escalation, and collaboration — using a café/restaurant as the working example.

🔗 Live file: `task-compass-cafe.html` (single-file, works fully offline — just open in any browser)

---

## 🎯 What This Project Teaches

Most "who does what" quizzes test job titles. This one tests **decision logic** — the same reasoning used in real organizational/process design and cross-functional workflow analysis:

- **Ownership** — identifying the person/role closest to a problem
- **Delegation** — knowing when a task needs to move beyond the obvious owner
- **Workflow sequencing** — modeling how information realistically travels through a team
- **Collaboration** — recognizing when a problem needs multiple stakeholders, not one decision-maker

This maps directly to skills used in **data analytics and business analysis**: root-cause identification, process mapping, stakeholder analysis, and structured decision frameworks.

---

## 🧩 How It Works

### Stage 1 — Who Owns This?
Drag-and-drop a role card into an ownership slot for a real café scenario (e.g. "a customer says their latte tastes burnt"). Every submission returns reasoning, not just correct/incorrect — the primary owner, *why* they own it, and which roles may assist.

### Stage 2 — Task Routing
Build a multi-step workflow by sequencing role cards (e.g. Server → Kitchen → Server → Host) for a task, then watch it animate through the organization. Explains why that routing order is realistic.

### Stage 3 — Collaboration Challenge
Larger, ambiguous problems (e.g. "customer satisfaction ratings suddenly dropped") require assigning up to 4 supporting roles instead of one owner — reinforcing that complex issues are rarely solved by a single person.

### Scoring & Reflection
Instead of a numeric score, the app tracks four qualitative dimensions — **Ownership, Delegation, Collaboration, Workflow Thinking** — visualized as animated bar charts, followed by a personalized reflection: what you understood well, where you over-assigned responsibility, where you underestimated collaboration, and one takeaway insight.

---

## 🛠️ Tech Stack

- **Pure HTML, CSS, Vanilla JavaScript** — zero dependencies, zero build step
- Native HTML5 Drag-and-Drop API + click-to-select fallback (mobile-friendly)
- CSS-only bar chart visualization, no charting libraries
- Fully offline — no CDN, no external API calls (deliberate design choice, see LEARNINGS.md)

---

## 🚀 How to Run

1. Download `task-compass-cafe.html`
2. Double-click to open in any browser
3. No install, no server, no internet required

---

## 📊 Why This Matters for Data/Analyst Roles

This project is really a **process-modeling exercise wearing a game's UI**: defining scenarios as structured data, mapping decision paths, and visualizing qualitative outcomes — the same instincts used when building stakeholder maps, RACI matrices, or workflow diagrams in a business analytics context.

---

## 🔗 Part of the ABTalks 60-Day Claude AI Mastery Challenge

Building one interactive AI-assisted app daily, documenting the process publicly.
Follow the full series: [github.com/sidharth0018](https://github.com/sidharth0018)
