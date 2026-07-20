# Day 46 — Autonomous Agent Studio (Multi-Agent Orchestration)

**Challenge:** ABTalks 60-Day Claude AI Mastery Challenge
**Day:** 46 / 60
**Category:** Agentic workflow design · Multi-agent orchestration · Prompt engineering

---

## 🎯 What I Built

**Autonomous Agent Studio** — a single-page app that runs a *real* multi-agent
pipeline live against the Claude API to write and self-improve a blog post,
with zero hardcoded rounds and zero fake/simulated scores.

Instead of one prompt doing everything, the work is split across **7 specialist
agents** that hand off state to each other in an actual loop:

```
Planner → Executor → [ Evaluator → Critic → Improver ]⟲ → Final Reviewer
                              ↑___________________|
                        (loops until a stop condition fires)
```

- **Planner** — turns a topic/audience/keyword brief into an outline + angle
- **Executor** — writes the first full draft from that brief
- **Evaluator** — scores each draft 0–100 on SEO + readability (JSON rubric output)
- **Critic** — finds specific weaknesses and concrete fixes (not vague praise)
- **Improver** — rewrites the full draft applying the Critic's fixes
- **Memory Manager** — tracks score deltas round-over-round to power the plateau check
- **Final Reviewer** — one-time editorial sign-off once the loop stops

## 🧠 Why This Was Interesting

Most "AI agent" demos I'd seen (and built earlier in this challenge) chain a
fixed number of calls in a fixed order. This one had to satisfy a much harder
constraint: **the number of rounds is a runtime result, not a design-time choice.**

That meant building a real stopping-condition state machine, checked in order,
every round:

1. **Plateau** — score improved by less than a configurable delta for 2
   consecutive rounds → diminishing returns, stop.
2. **Threshold** — score crosses the target set at setup → goal met, stop.
3. **Hard iteration cap** — a safety fallback only, never the intended ending.

Whichever fires first wins, and the UI names the *exact* reason — not just
"done."

## 🛠️ How It Was Built

1. **Interview-first UX** — before generating anything, the app conducts a
   guided MCQ interview (workflow type → output format → success metric →
   stopping condition → auto-design vs. customize agents) so the pipeline is
   configured to the user's actual need instead of one-size-fits-all.
2. **Production-quality system prompts per agent** — each agent gets a tightly
   scoped system prompt (rubric for Evaluator, strict output-shape rules for
   Improver, etc.) so outputs are parseable and specific.
3. **A real `while(true)` loop** — Evaluator → Critic → Improver re-run with a
   **live `fetch` call every single time**, threading forward: prior score,
   prior evaluator summary, prior critic fixes, and the current draft. No step
   is cached, mocked, or pre-written.
4. **Live dashboard** — animated cyclic workflow diagram (not a straight
   pipeline — a real loop with a return arrow, branching off to Final Reviewer
   only once a stop condition fires), round-by-round history, activity log,
   memory update cards, and an open-ended round indicator ("Round 3 — checking
   stop condition…", not "Round 3 of 5").
5. **Closing report** — final blog post, agent performance summary, execution
   stats (rounds run, score trajectory, total API calls), architecture
   writeup, and extension ideas — auto-generated from the actual run data.

## 💡 Key Learnings

- **Runtime-determined loops need explicit, ordered stop checks** — "stop when
  it's good enough" is not a spec until you decide what "good enough" means
  and in what priority (plateau vs. threshold vs. safety cap all had to be
  checked in a fixed order every round, not as a first-match-wins race).
- **State threading is the actual hard part of multi-agent design** — the
  interesting engineering wasn't calling the API repeatedly, it was making
  sure each agent's *context* (score + critique + draft) flowed correctly
  into the next agent's prompt, every round.
- **JSON-only Evaluator output needs a lenient fallback parser** — LLMs
  occasionally wrap JSON in prose or code fences despite instructions; a
  simple regex fallback stopped one bad response from crashing the whole run.
- **A widget/artifact sandbox ≠ a portable app** — code that calls the Claude
  API "with no key" only works inside the Claude.ai artifact renderer, which
  authenticates those calls on the user's behalf. The exact same file opened
  locally (`file://…`) has no auth and no way to make that cross-origin call —
  a good reminder to be explicit about *where* a generated app is meant to run
  before shipping it as a "just open this file" deliverable.

## 🧩 Tech Stack

- Vanilla HTML / CSS / JS (single self-contained file, no external libraries)
- Live calls to `https://api.anthropic.com/v1/messages` (Claude Sonnet)
- Hand-drawn SVG workflow diagram with live "active agent" highlighting
- Dark-mode, responsive, retry/error-handling built in

## 📂 Files in This Folder

| File | Purpose |
|---|---|
| `autonomous-agent-studio.html` | The full working app |
| `Day46.md` | This summary |
| `LEARNINGS.md` | Deeper technical learnings & reflections |
| `prompt.md` | The exact interview prompt used to spec the app |

---

**◀ [Day 45: AI Decision Strategist](../Day45/Day45.md)** | **[Day 47 →](../Day47/Day47.md)**
