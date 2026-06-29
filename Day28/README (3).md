# Day 28 — Hospital Admission Readiness Simulator

Part of the **#ABTalks 60-Day Claude AI Mastery Challenge** — one AI-assisted project, every day, documented and shipped publicly.

🔗 Live file: `hospital-admission-readiness-simulator.html` (single-file, open directly in any browser)

---

## 🩺 What This Is

A single-file HTML/JS simulator that puts you in the seat of a **Hospital Admission Coordinator**. You set up a patient case (diagnosis, admission type, Prior Authorization status), and the tool walks you through the real operational workflow hospitals use to decide: *is this patient actually ready to be admitted?*

It's built as a **US healthcare RCM (Revenue Cycle Management) training tool** — same domain as Day 26 and Day 27's Prior Authorization simulators, but this one focuses on the **admission readiness** stage rather than just PA approval.

> ⚠️ All provider names, physician names, and payer details in the tool are **fictional/illustrative training data** — not real entities.

---

## 🎯 Why I Built This

Healthcare RCM and Utilization Review (UR) are dense, jargon-heavy domains that are genuinely hard to learn from a textbook. I wanted to see if Claude could help me turn a wall of compliance rules (CMS 2-Midnight Rule, InterQual/Milliman medical necessity criteria, PA appeal workflows) into something **interactive and intuitive** — learn by doing, not by reading a policy PDF.

This also continues testing a hypothesis from Days 26–27: **can a single AI-generated HTML file encode a genuinely complex, multi-branch business workflow without a backend?**

---

## 🧩 Core Features

| Feature | What it does |
|---|---|
| **Case Setup** | Pick Provider, Attending Physician, Diagnosis, Admission Type, PA Status, Admission Date |
| **CMS 2-Midnight Rule alert** | Auto-triggers for Observation admissions — flags cost-sharing, SNF eligibility, and MOON notification requirements |
| **Weighted Readiness Score** | PA 25% · Documentation 20% · Physician Orders 20% · Insurance 15% · Consent 10% · Bed 10% |
| **PA Branching Logic** | Approved → proceed · Pending → Follow Up/Upload Docs/Contact Physician · Denied → Review Reason/Contact Insurance/Submit Appeal |
| **Hard Business Rule** | Denied PA + ICU admission is **capped at 69%** — can never reach Admit from admin tasks alone, no matter how many other boxes are ticked |
| **Medical Necessity Note** | Acute MI / CHF cases surface an InterQual/Milliman criteria reminder before UR review |
| **7 Workflow Actions** | Assign Bed, Verify Insurance, Upload Documentation, Complete Consent, Contact Physician, Notify Nursing, Prepare Patient Arrival — each with a live action log |
| **Risk Tracking** | 4 live risk categories (Documentation / Insurance / Bed / Clinical) — Clinical Risk auto-escalates for MI, CHF, and ICU cases |
| **9-Step Timeline** | Visual progress tracker from PA Review → Admission Complete |
| **Care Coordination Cards** | Attending, Case Manager, Nursing, Utilization Review (explicitly naming concurrent review, denial risk ID, InterQual, Milliman), Discharge Planner |
| **Governance Snapshot** | Unlocks at ≥75% readiness — shows illustrative industry benchmarks (PA turnaround, denial rate, rework cost) |
| **Final Decision Engine** | ≥90% → ✅ **Admit** (full summary) · <90% → ⚠️ **Not Ready** (missing items, required actions, remaining risks) |

---

## 🛠️ Tech Stack

- **HTML5** — single file, zero build step
- **Tailwind CSS (CDN)** — utility-first styling, consistent design system with Days 26–27
- **Vanilla JavaScript** — all state management, scoring logic, and branching done client-side, no framework

No backend, no database, no dependencies beyond the Tailwind CDN script tag. Open the file, it runs.

---

## 🧠 How It Works (Logic Summary)

1. **Setup → Initial Analysis**: On submitting the case, readiness is calculated but deliberately capped between 30–60% to mirror reality — you can't know if a case is "ready" before any tasks are actually done.
2. **Score recalculates live** every time a workflow action is completed or the PA status changes.
3. **PA status drives the ceiling**: Denied PA caps the score at 74% regardless of other tasks; Denied PA + ICU drops that ceiling to 69%.
4. **Clinical Risk** is diagnosis-aware — Acute MI, CHF, and ICU admissions are flagged High risk by default, independent of how many admin tasks are completed, because clinical risk isn't an admin problem.
5. **Final decision** only flips to Admit at 90%+, forcing the user to actually resolve PA, documentation, orders, insurance, consent, and bed — there's no shortcut.

---

## 📚 Related Days

- **Day 26** — Prior Authorization Workflow Simulator (drag-and-drop, gamified)
- **Day 27** — Prior Authorization Workflow Simulator (narrative branching story format)
- **Day 28** — Hospital Admission Readiness Simulator *(this project)* — extends the PA logic from Days 26-27 into the next stage of the patient journey: full admission readiness

---

## 🚀 How to Run

1. Download `hospital-admission-readiness-simulator.html`
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari)
3. No installation, no server, no API keys needed

---

## 📌 Part of

**#ABTalks 60-Day Claude AI Mastery Challenge**
Follow the full build log → [GitHub: sidharth0018](https://github.com/sidharth0018)
Daily progress on LinkedIn.
