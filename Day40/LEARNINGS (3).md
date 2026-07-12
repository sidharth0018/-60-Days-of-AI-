# Day 40 — Learnings

## 1. Interviewing before building beats a single big prompt
Asking one MCQ-style question at a time (domain → niche → audience/outcome → inputs → output → tone) produced
a much sharper brief than a single "describe your assistant" prompt would have. Each answer narrowed the
design space enough that by the last question, the UI and system prompt basically wrote themselves.

## 2. The system prompt is a product spec, not an afterthought
Writing the assistant's "brain" as its own deliverable — with a strict JSON output schema — forced me to
think through edge cases (off-topic input, vague input, prompt injection) *before* writing any UI code,
instead of discovering them later as bugs. Strict-JSON output also removes an entire class of parsing bugs
on the frontend: no regex, no guessing where the model's answer starts.

## 3. "No generic chatbot box" is a real design constraint worth holding
It's tempting to default to a chat bubble UI for anything AI-powered. Grounding the interface in the
subject's own object — an index card for a study tool — made the tool feel purpose-built instead of a
Claude wrapper, and it forced better information hierarchy (summary → example → practice, in that order)
because a physical card can't just scroll infinitely like a chat log.

## 4. Redirect states are as important as success states
Designing an explicit `status: "redirect"` path for off-topic or injected input meant the UI never has to
guess whether a bad response is an error or a boundary — it can show a calm, on-brand "let's stay on topic"
message instead of an ugly error or, worse, an off-scope answer.

## 5. What I'd extend next
- Persist generated cards per topic using `window.storage` so this becomes a real personal flashcard deck
  across sessions.
- Add a second API call that grades typed answers to the practice questions — turning this from a
  single-shot generator into a short tutoring loop.
- Add a code-execution tool so SQL/Python examples in the "worked example" section can actually run against
  sample data instead of being static text.

## Tomorrow (Day 41)
Continue the challenge — next build TBD.
