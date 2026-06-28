# Day 26 — Learnings

## What I built
A single-file, drag-and-drop simulator of the healthcare Prior Authorization workflow — Patient/Provider/Payer lanes, 4 scenarios, a weighted approval/denial engine, appeal/peer-to-peer paths, and a full session summary. Pure HTML/CSS/vanilla JS, no frameworks, no localStorage.

## Why this project
I wanted a build that wasn't just a UI exercise but modeled a real, messy multi-party business process with branching outcomes — closer to the kind of domain-modeling and state-machine thinking that comes up in data/software roles, rather than a static dashboard or form.

## Prompting approach that worked
- Gave one detailed, structured spec up front (lanes, stages, scenarios, required UI elements, hard technical constraints like "no CDNs, no localStorage") rather than building it up turn by turn. Claude generated a complete, working single file in one shot from that.
- Constraints mattered more than I expected — explicitly banning localStorage and frameworks forced a cleaner in-memory state object, which made the whole app easier to reason about (and easier for Claude to debug later from a screenshot).

## Bug I hit — and how it got found
After testing in-browser, I dragged the case card from "Medical Necessity" to "Document Collection" and nothing happened — no error, just a silent stall. I shared a screenshot of the stuck state rather than describing the bug in words.

From that screenshot alone, Claude correctly diagnosed the root cause: my drop-handling logic had a rule that treated "dropping into the same lane" as a harmless no-op. But two consecutive stages (Medical Necessity → Document Collection) both happen inside the *same* Provider Lane — so that "safety" rule was silently blocking a legitimate forward move. The fix was a one-line logic change: validity should be based on whether the target lane matches the *next stage's* lane, not on whether it differs from the *current* lane.

**Takeaway:** a screenshot of broken behavior was faster and more precise than trying to describe the bug myself — the visual state (which lane the card was stuck in, which stage was highlighted) was enough context for a correct diagnosis on the first try.

## Key technical decisions
- Modeled the whole workflow as an ordered `STAGES` array with a `lane` property per stage, so the progress tracker, the drag-and-drop validity check, and the educational copy could all be driven from one source of truth instead of three separate hardcoded paths.
- Made the payer decision "engine" probabilistic but explainable: a base necessity-strength score per scenario, adjusted by document completeness and prior pend count, then rolled against threshold bands for approve/pend/deny — close enough to real utilization-review logic to be a useful mental model, simple enough to read in a few lines of code.

## What I'd do differently next time
- Build in a quick self-test pass (mentally walking the state machine stage-by-stage) before first share, instead of relying on the first live test to catch lane-mapping bugs.
- Could extend this with a difficulty/insurer-policy toggle to vary necessity thresholds — good candidate for a "Day 26 v2" revisit later in the challenge.

## Skills reinforced
- State-machine design for multi-actor workflows
- Debugging from visual evidence (screenshot-only bug reports)
- Writing tight functional specs that an AI tool can execute end-to-end in one pass
- Probabilistic decision modeling expressed in plain, readable code
