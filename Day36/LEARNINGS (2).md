# Day 36 — Learnings

## Prompt Engineering Takeaways

- **Constraint-first prompting works well for sensitive domains.** Explicitly telling Claude "this is educational only, never diagnose, use reflective language" up front shaped every downstream generation — the scenario copy, the scoring blurbs, and even the final disclaimer all stayed in that reflective register without needing repeated reminders.
- **Naming the exact flow (Start → Ch1 → Ch2 → Ch3 → Final) gave Claude a clear state machine to build against.** Vague "make a quiz app" prompts tend to produce single-screen apps; specifying chapters up front produced a proper multi-screen app with its own internal navigation and progress tracking.
- **Listing the 5 target categories by name (Analytical, Emotional Intuitive, Overthinking Loop, Action-First, Balanced Reflective) meant Claude designed both the scenario weighting system and the priority/timeline cards around them consistently** — every interaction contributes to the same 5-bucket score object.

## Technical Takeaways

- **Native HTML5 Drag-and-Drop alone isn't enough for mobile** — `dragstart`/`dragover`/`drop` events don't fire from touch input. The fix is a parallel `touchstart`/`touchmove`/`touchend` handler set that manually computes drop targets via `document.elementFromPoint()`.
- **Keyboard accessibility for drag interfaces needs a separate interaction model**, not just a "focus the draggable" patch. I had Claude add explicit ▲/▼ buttons plus Arrow key handlers as a fully independent way to reorder cards — useful pattern for any future ranking/sorting UI.
- **`prefers-reduced-motion` should be checked on load AND exposed as a manual toggle** — some users want reduced motion without changing their OS-level setting.
- **Weighted scoring across multiple interaction types (multiple choice + drag ranking + drag timeline) can all funnel into one shared score object** if each contributor calls a common `addScore(weights)` function — kept the scoring logic simple even though the input mechanisms were very different.

## What I'd Improve Next Time

- Add a way to save/export the final journal (e.g., as an image or text summary) for sharing.
- Consider persisting state in `localStorage` so a user could resume a session (currently in-memory only, by design, since this needed to work as a single portable file without needing storage permissions).
- Could extend chapter 3's timeline into a visual "thinking process" flow diagram instead of plain slots, for stronger visual storytelling.

## Relevance to My Data Analyst / Data Science Career Track

- The weighted scoring + percentage breakdown logic in the final screen (`score/total * 100`, sorted, rendered as bars) is directly the same category of logic used in survey scoring, NPS breakdowns, and categorical distribution charts — the kind of aggregation logic that shows up in dashboarding work.
- This project is a good candidate to eventually re-express as a **Power BI or Excel dashboard exercise**: take the same 5-category scoring model, generate simulated response data across many users, and build a distribution/breakdown dashboard — bridging this JS prototype into the BI tooling I'm actively upskilling in.
