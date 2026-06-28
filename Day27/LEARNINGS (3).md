# Day 27 — Learnings

## What I built
A narrative, branching chat simulation of a Prior Authorization journey — 8 scenes, 2 characters, choice-driven dialogue, built single-file with Tailwind CDN + vanilla JS on top of a strict "append-only DOM" constraint.

## Why this project
Day 26 modeled the PA process as a system/workflow (lanes, stages, a decision engine). Day 27 deliberately re-told the *same domain* as a human story instead — same subject matter, completely different format. Doing both back-to-back was a useful exercise in seeing how the same real-world process can be taught either as a system diagram or as a narrative, and which one lands better for which audience.

## Prompting approach that worked
- Gave Claude very specific, non-negotiable technical constraints up front: characters' fixed screen positions, narrator text must never be a chat bubble, and — most importantly — "never call `innerHTML =` on the chat container, use `createElement` + `appendChild` for every new element." Stating the *implementation rule*, not just the visual outcome, meant the generated code respected the constraint structurally rather than just looking right by accident.
- Pre-loaded each scene with the exact factual content I wanted included (the AMA citation, the "no pharmacy involved" detail, the staff-hours stat) rather than asking Claude to "explain PA" generically. This kept the educational content accurate and specific instead of generic filler.
- Referencing "design same as previously established" let Claude carry over the visual language from Day 26 without me having to redescribe the whole color system from scratch.

## Key technical decisions
- Built small composable render functions (`appendNarrator`, `appendChatBubble`, `appendInfoCard`, `appendSceneTitle`) that all funnel through `createElement`/`appendChild` — so the append-only rule is enforced once at the function level instead of needing to be remembered at every call site.
- Used `removeChild` in a loop for the restart flow instead of `innerHTML = ""`, since the constraint was about the chat container specifically — worth thinking through edge cases like "how do you reset state" before they become a rule violation.
- Kept the "choice affects dialogue" mechanic intentionally lightweight (branches the next few lines, not the overall story outcome) to keep scope realistic for a single day's build — flagged as a natural "v2" extension.

## What I'd do differently next time
- Could make the choices affect the *outcome* of the story (e.g., a less-prepared choice leading to a second denial) rather than just the flavor dialogue — more realistic, and would reinforce the "documentation matters" lesson even harder.
- Consider adding a downloadable "transcript" export at the end, so a user could save their specific playthrough.

## Skills reinforced
- Enforcing implementation-level constraints (not just visual/output constraints) through precise prompting
- DOM manipulation patterns and why "append-only" matters for transcript-style UIs (chat logs, audit trails)
- Translating the same domain knowledge into a second, very different UX format without losing accuracy
- Embedding real citations and statistics naturally into a conversational narrative instead of as a dry appendix
