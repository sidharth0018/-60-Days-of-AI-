# Day 49 — Learnings

## 1. Interview-before-build beats build-then-iterate
Answering 5 MCQs about my own AI usage before any code was written meant the categories, wording, and even the empty states matched my real workflow — not a generic "AI toolkit" template. Self-interviewing works the same way it works for client projects.

## 2. The bottleneck was retention, not access
I assumed my problem was "not knowing good prompts." The real bottleneck surfaced in the interview: I already ask good questions, I just have no system to keep what I learn from the answers. That reframed the whole build — every workflow template ends in a structured output (note card, checklist) meant to be saved, not just read once.

## 3. "Explain every building block, twice"
Instructing the AI to show each block's purpose both in the picker *and* inside the assembled block (not just once) made the Prompt/Loop Builder usable without a tutorial. Small UX rule, big clarity gain.

## 4. Local-first tools remove a whole category of decisions
No backend meant no auth, no hosting, no privacy questions — just `localStorage` + export/import. For a personal tool, that constraint sped up the build and made "can anyone see my saved prompts" a non-issue.

## 5. Next time
Add a "usage streak" or lightweight analytics view so the Playbook itself demonstrates the retention habit it's trying to build, not just enable it.
