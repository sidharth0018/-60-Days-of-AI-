# Day 28 — Learnings

## 🎯 What I Was Trying to Learn

After Days 26 and 27 (both Prior Authorization simulators), I wanted to push further into the **admission readiness** stage of the patient journey, and specifically test whether Claude could hold and correctly enforce a **non-obvious business rule** — a denied PA + ICU combination capping the score at 69% — across a fully dynamic, interactive scoring system.

---

## 🔑 Key Learnings

### 1. Weighted scoring with hard caps is harder to spec than it looks
Asking for "weighted readiness score" is easy. Asking for "weighted score, EXCEPT this one combination can never cross a threshold" forces the logic into two layers: the base weighted calculation, and then a **post-hoc business rule override**. I learned to separate these explicitly in the prompt instead of trying to bake the exception into the weights themselves — much cleaner and easier to debug.

### 2. Domain jargon needs to be load-bearing, not decorative
The instructions required the UR card to *name* concurrent review, denial risk identification, InterQual, and Milliman — not just imply them. This is a useful pattern for any compliance-adjacent build: specific terminology in healthcare/finance/legal isn't optional flavor text, it's often the actual deliverable a recruiter or domain expert is checking for.

### 3. Conditional UI based on admission type is a recurring pattern
The CMS 2-Midnight Rule banner only appears for Observation admissions. This is the third project in a row (after Days 26-27) where Claude needed to correctly gate a regulatory disclosure behind a specific user selection — reinforced that conditional compliance messaging is a real, repeatable UI pattern in healthcare software, not a one-off.

### 4. State machines benefit from "auto-resolution" logic
Rather than making the PA Pending → Approved transition a single button click, I had it auto-resolve only once *two* prerequisite actions were completed (Upload Docs + Contact Physician). This mirrors how real authorization workflows actually behave — approval isn't a button, it's a consequence of completing the right steps — and made the simulator feel more like a real system than a toy.

### 5. Testing edge cases matters more than testing the happy path
The most interesting (and most instructive) scenario isn't "PA approved, everything goes smoothly" — it's "Denied PA + ICU," where the tool has to actively *refuse* to let the user reach 90% no matter how many other tasks they complete. Building and testing that constraint taught me more about scoring logic design than the standard approval flow did.

---

## 🐛 Debugging Notes

- Initial readiness range (30-60%) had to be explicitly clamped after the weighted calculation, since raw weighted scores could fall outside that band depending on default task states.
- The PA tag color/label rendering needed a consistent token order (3 CSS classes + label words) — easy to break with new statuses, so kept the badge map structured rather than hand-writing each case.
- Governance Snapshot only firing at ≥75% (not on initial load) required moving its render check into the same `updateAll()` cycle as the score, not the page mount.

---

## 🔁 What I'd Do Differently Next Time

- Add a visible "reset/restart case" button to make testing multiple diagnosis scenarios faster, rather than relying on a full page refresh.
- Consider persisting the action log per case so multi-scenario testing produces a comparable side-by-side history.

---

## 📌 Part of

**#ABTalks 60-Day Claude AI Mastery Challenge** — Day 28 of 60.
