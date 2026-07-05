# Day 35 Learnings — Prompt Puzzle

## 1. A single stray escape character can silently break an entire single-file app
The most important lesson today wasn't about prompting — it was about debugging. I hit a "blank white page" after generating the app. Root cause: a JS string like `'That\'s the optimized prompt.'` had an incorrectly escaped apostrophe (`\\'` instead of `\'`), which broke the entire `<script>` block's parsing. Since everything lives in one file, one syntax error anywhere kills the whole page silently (no visible error unless you open DevTools console).

**Takeaway:** For single-file HTML apps, always validate the extracted JS separately before shipping. I used `node --check` on the extracted script block to catch this instantly instead of guessing.

```bash
# Quick way to validate JS inside a single-file HTML app
python3 -c "
import re
content = open('app.html').read()
js = re.search(r'<script>(.*)</script>', content, re.DOTALL).group(1)
open('/tmp/test.js','w').write(js)
"
node --check /tmp/test.js
```

## 2. Prefer double quotes over escaped single quotes for strings with apostrophes
Instead of `'That\'s correct'`, just write `"That's correct"`. Removes an entire class of escaping bugs. Small habit, real payoff.

## 3. Designing "Prompt DNA" as a teaching device
Rather than just showing a raw score, breaking performance into named traits (Specificity, Structure, Efficiency, Speed) makes feedback feel personalized and actionable — this mirrors how I want my own dashboards/reports to communicate insights to non-technical stakeholders (a skill directly relevant to Data Analyst interviews).

## 4. Distractor design is itself a prompting lesson
Writing "distractor blocks" (e.g., "make it sound impressive," "use as many pandas tricks as possible") forced me to think about *anti-patterns* in prompting — vague flattery instructions, scope creep, irrelevant asks. Naming these anti-patterns explicitly is something I can now reuse when reviewing my own prompts for real work.

## 5. Scenario objects as reusable content architecture
Storing each scenario as one JS object (desiredOutput, correctBlocks, distractorBlocks, weakPrompt, optimizedPrompt, overEngineeredPrompt, principle) made the whole app trivially extensible — adding a new domain is just adding new objects, no logic changes. This "data-driven UI" pattern is directly transferable to dashboard/report generation work.

## Skill Tags
`javascript-debugging` `single-file-html-architecture` `prompt-engineering-principles` `ui-ux-microinteractions` `data-driven-content-design`
