# Learnings — Day 46: Content Intelligence Studio

## 1. Multi-agent pipelines beat single-prompt analysis
Splitting one big "analyze this content" prompt into 5 focused reviewer prompts (strategist, visual, copy, audience, recruiter) produced noticeably sharper, more specific feedback than asking one prompt to cover everything at once. Each system prompt could stay narrow and opinionated instead of hedging across concerns.

## 2. Ditch JSON for long-form LLM output
Asking Claude to return JSON containing long free-text fields (rewrites, hooks, checklists) is fragile — quotes, apostrophes, line breaks, and emoji inside the text regularly break naive `JSON.parse`. Switching to a **labeled plain-text section protocol** (`LABEL: value`, `LIST_LABEL:\n- item\n- item`) and parsing it with regex was more resilient and easier to debug when something didn't match — I could just look at the raw text.

## 3. Dynamic pipelines from user answers
Instead of a fixed reviewer team, the app swaps reviewers based on stated goal (`Recruiter / Hiring Lens` vs `Growth & Conversion Analyst`) using a simple keyword check on the goal string. Small conditional logic in pipeline *assembly* is fine — the constraint is that the actual *analysis content* must never be hardcoded, only the choice of which specialist gets asked.

## 4. Real image analysis needs the image sent every time
Early draft only sent the image to the first reviewer and reused text summaries after that — visual reviewers gave vague feedback. Sending the base64 image block in **every** relevant API call (not just once) made visual feedback concrete and specific ("the CTA button blends into the background" vs "consider improving contrast").

## 5. UX for waiting matters as much as the output
A staged pipeline UI (icon → spinner → checkmark per reviewer) plus a live timestamped log made a 30–60 second wait feel transparent instead of like a frozen page. Small thing, but it changes how trustworthy the tool feels.

## 6. MCQ-first interviews reduce abandonment
Asking 5 tap-to-select questions before any upload (rather than one long form) meant the tool could tailor its language and reviewer team before ever seeing the content — and kept the intake step fast on mobile.
