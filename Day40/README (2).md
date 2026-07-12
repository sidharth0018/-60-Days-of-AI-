# Day 40 — Deskside: AI Assistant Builder (Concept Tutor for Data Analyst Interviews)

Part of the **ABTalks 60-Day Claude AI Mastery Challenge** — one AI-assisted build every day.

## 🎯 What I built

Today I acted as an **AI Assistant Builder**: instead of building one specific app, I designed and shipped a
reusable *process* for turning an idea into a fully working AI product — system prompt + live UI + docs —
then used that process to build **Deskside**, a concept tutor for Data Analyst / Data Science interview prep
(SQL, statistics, DSA, general CS fundamentals).

The output is a single self-contained `concept-tutor.html` file that:
- Interviews the "product owner" (me) one question at a time to scope the assistant before building anything
- Ships a production-quality **system prompt** as the assistant's brain
- Calls the **Claude API live** (`/v1/messages`) from the browser, no backend
- Renders answers into a **custom, on-brand UI** — not a generic chat box
- Handles loading / error / empty / off-topic states gracefully
- Includes a collapsible **"How this was built"** panel documenting the design decisions

## 🧠 The core idea: interview → prompt → UI → docs

The build followed a 4-stage pipeline that's reusable for *any* niche AI assistant, not just this one:

1. **Interview** — ask one multiple-choice question at a time (domain → niche → audience/outcome → inputs →
   output shape → tone) instead of one big open-ended brief. This mirrors real product discovery and produces
   answers precise enough to design against.
2. **Brain** — write the system prompt as its own artifact: role, strict output schema, scope guardrails,
   vague-input handling, and abuse/prompt-injection handling — all *before* touching any UI code.
3. **Interface** — build a single HTML file whose visual metaphor comes from the subject itself (an index
   card / study desk for a tutor tool), not a template chat window.
4. **Docs** — ship a collapsible in-app section explaining *why*, so anyone opening the file (or my GitHub
   profile) understands the reasoning, not just the output.

## 🃏 Why "Deskside" looks the way it does

Most AI tool UIs default to a chat bubble. A study tool's honest metaphor is the object people actually
study from — so this became a **desk with an index-card stack**:

- Deep ink-navy "desk" background, warm paper-cream card, mustard accent for actions, teal for structural
  dividers — deliberately avoiding the two most common "AI-generated" looks (cream + terracotta, or
  black + neon).
- Serif type for headings (textbook voice), monospace for labels/code (data-tool voice).
- Practice questions are collapsible hint-reveals, so the answer doesn't spoil itself before you've tried.

## 🛠️ How the assistant's brain is scoped

The system prompt forces the model to return **strict JSON** matching a fixed schema (topic, difficulty,
summary, worked example, practice questions + hints) — no prose, no markdown fences — so the response is
directly renderable into the UI with zero fragile text-parsing.

It also handles the three edge cases every real assistant needs:
- **Off-topic input** → returns a `redirect` status with a friendly message instead of forcing an answer.
- **Vague input** ("sql", "data stuff") → picks the most reasonable interpretation for a Data Analyst
  interview context and states the assumption, rather than stalling on a clarifying question.
- **Prompt injection / role-change attempts** → explicitly ignored; falls back to the same redirect path.

## 📁 Files in this folder

| File | Purpose |
|---|---|
| `concept-tutor.html` | The full working app — open directly in a browser |
| `LEARNINGS.md` | What I learned building this, and what I'd extend next |
| `Day40.md` | Daily challenge log entry |

## 🚀 Try it

Open `concept-tutor.html` in any browser. Type a topic (e.g. *"SQL window functions"* or *"hypothesis
testing"*), pick a difficulty, and hit **Explain this →**.

## 🔧 Tech stack

Plain HTML / CSS / JS — no frameworks, no build step, no external libraries. Live calls to the Claude API
(`claude-sonnet-4-6`) directly from the browser.

---

🔗 **Follow the full 60-day challenge:** GitHub: [sidharth0018](https://github.com/sidharth0018) · LinkedIn:
[sidharth-kumar-501768287](https://linkedin.com/in/sidharth-kumar-501768287)
