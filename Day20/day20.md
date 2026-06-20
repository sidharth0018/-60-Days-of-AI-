# Day 20/60 — ABTalks Claude AI Mastery Challenge
## Building a Face Puzzle Game with Claude: Prompt → Production Code

---

## 🎯 What I Built

A fully working, single-file **Face Puzzle Game**: webcam capture → snapshot → sliceable puzzle (3×3/4×4/5×5) → drag-and-touch gameplay → timer/move tracking → win detection → persistent leaderboard. Zero dependencies, zero backend, pure HTML/CSS/JS.

---

## 🧠 Key Learnings

### 1. Writing a "spec-grade" prompt gets spec-grade output
Instead of "build me a puzzle game," I broke the request into 6 numbered feature blocks (camera, generation, controls, timer, win detection, polish) with explicit sub-bullets for each. This is the same discipline as writing a PRD before coding — Claude (or any engineer) builds more completely and with fewer gaps when requirements are itemized rather than described loosely.

**Takeaway for interviews/work:** vague tickets produce vague code. Specific acceptance criteria produce complete features in one pass.

### 2. Browser permission APIs need defensive coding, not happy-path coding
`getUserMedia()` can fail in at least three distinct ways — permission denied, no device found, device already in use — and each needs a different user-facing message. I learned to think in terms of **error taxonomy**, not just "try/catch and hope."

### 3. A "puzzle" isn't always a sliding-tile problem
Classic 15-puzzles need parity checks to guarantee solvability (you can't reach every permutation by sliding one blank tile). But this game allows **any piece to swap with any piece** directly — which means every shuffle is automatically solvable. Recognizing which constraint model applies *before* writing shuffle logic saved a lot of unnecessary complexity.

### 4. Unifying mouse + touch input around one interaction model
Rather than writing separate logic trees for desktop drag vs. mobile touch, the cleanest pattern is: abstract both into `pointerDown / pointerMove / pointerUp` style handlers, then attach `mousedown/mousemove/mouseup` and `touchstart/touchmove/touchend` listeners that just call the same shared functions with different event coordinates. This is a reusable pattern for any draggable UI element, not just puzzles.

### 5. Image slicing without pre-cutting files
Instead of physically cropping an image into N separate files, each "piece" is a full-size `<div>` with `background-image` set to the *whole* photo, and `background-position` shifted to reveal only its slice. This is a much lighter-weight technique than canvas-cropping each tile individually, and it's a pattern worth reusing for any tile-based image UI (galleries, before/after sliders, etc.).

### 6. `localStorage` as a lightweight leaderboard/database
For client-only apps with no backend, `localStorage` is enough to persist structured data (sorted, capped lists, JSON objects) across sessions. Good reminder that not every "save data" feature needs a database — sometimes the browser *is* the database.

### 7. From code → reusable GitHub artifact
Beyond just generating code, I practiced the packaging habit: README with feature list, tech stack table, run instructions, "what I learned" section, and clean file structure — the same repeatable format I'm using across all 20 days. Consistency in documentation format is itself a skill that compounds.

---

## 💡 Why This Matters for My Data Analyst / Data Science Goal

This wasn't a data project, but the muscle being trained — **breaking ambiguous requirements into structured, testable specs**, and **packaging work into reviewable, documented artifacts** — is exactly what's expected in any analyst or SWE role at companies like Razorpay, Groww, or Deloitte. Clear documentation habits and structured thinking transfer directly into how I'll write technical reports, README's for analysis notebooks, and stakeholder-facing summaries.

---

## 📋 LinkedIn Post (Day 20/60)

> 🧩 Day 20/60 — ABTalks Claude AI Mastery Challenge
>
> Today I asked Claude to build something fun: a webcam-powered Face Puzzle Game — snap a selfie, scramble it into a 3×3/4×4/5×5 grid, then drag-and-drop (mouse OR touch) to solve it. Live timer, move counter, win detection, and a persistent localStorage leaderboard. Single HTML file, zero dependencies.
>
> The real learning wasn't the puzzle — it was *how* I asked for it:
>
> ✅ I broke the ask into 6 numbered feature blocks instead of one vague sentence — and got complete, working code in one pass instead of three rounds of "you forgot X."
>
> ✅ Learned why classic sliding puzzles need solvability checks, but a swap-anywhere puzzle doesn't — picking the right constraint model before writing shuffle logic.
>
> ✅ One pattern, two input types: unified mouse-drag and touch-drag into the same handler functions instead of duplicating logic.
>
> ✅ Image slicing without cutting files — just shifting `background-position` on full-size divs.
>
> ✅ `localStorage` as a "good enough" database for client-only persistence.
>
> Code + README pushed to GitHub (sidharth0018) as part of the 60-day build-in-public series.
>
> The bigger pattern I keep relearning: specific, structured prompts (and specs) beat vague ones — in code, and in every analyst report I'll ever write.
>
> #BuildInPublic #ABTalks60DayChallenge #ClaudeAI #WebDev #DataAnalyst #LearningInPublic

---

*Day 20 of 60 complete. On to Day 21.* 🚀
