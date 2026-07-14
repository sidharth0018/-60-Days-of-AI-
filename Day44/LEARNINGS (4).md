# Day 44 — Learnings

## Prompt engineering

- **Forcing specificity with a fixed critique structure.** Asking an LLM to "give feedback" tends to produce vague encouragement. Locking the roast into ❌ problem / 🧠 why it hurts / 🔍 invisible cost, and requiring the model to quote the user's own words back at them, produced concrete, non-generic critique instead of "this could be stronger."
- **An explicit no-fabrication rule changes output quality, not just safety.** Telling the model to never invent achievements or metrics meant that when my Experience section had nothing concrete to point to, the output didn't paper over the gap with a fake number — it named the gap as the single highest-leverage fix. That's more useful than a polished lie.
- **Sequencing input collection one question at a time** (headline → About → Experience → skills → goal) kept each answer focused and gave the model a clean, complete input set before it started scoring — versus asking for everything in one message and getting a rushed, partial audit.
- **Ask-then-generate order for structured deliverables.** For a multi-part output (roast, rebuild, scorecard, plan, summary), gathering all inputs first and generating the full pipeline in one pass kept every section internally consistent — the rebuild referenced the exact scores from the roast, and the plan referenced the exact rewrite.

## Product / UX

- Long structured text (roast + rewrite + 7-day plan + summary) is genuinely hard to use as a wall of markdown. Converting it into a tabbed HTML report with copy buttons on each rewritten block turned "read this and remember to copy the right bits" into "click, copy, paste."
- A capped score with a stated reason ("Experience caps at 7 until you add one real deliverable") is more trustworthy than an inflated score — it signals the tool isn't just flattering the user.

## For tomorrow

- Consider letting the tool accept a second pass — rerun the audit once the user has added a real project, and diff the new score against today's baseline.
