# Day 18/60 — AI Brain Dump → Action Planner

**ABTalks 60-Day Claude AI Mastery Challenge**
📅 Date: 18 June 2026 | 👤 GitHub: [sidharth0018](https://github.com/sidharth0018)

---

## What I Built

An AI-powered **skill** (`/brain-dump-action-planner`) that transforms raw, messy notes from **any format** into structured action plans, risk registers, and open question trackers — rendered as interactive HTML dashboards with filtering and source attribution.

---

## Formats Tested

| Format | Input Type | Action Items | Conflicts Found |
|---|---|---|---|
| Meeting transcript | Formal multi-speaker | 8 | 3 |
| Brain dump | Stream-of-consciousness | 10 | 1 |
| Bullet notes | Structured study session | 9 | 0 |
| Voice memo | Filler-word transcript | 4 | 1 |
| WhatsApp chat | Informal group chat | 6 | 2 |
| **Total** | | **37** | **7** |

---

## Key Outputs

- ✅ Per-format dashboards: summary · action items · risks · open questions
- ✅ Consolidated review across all 5 sources (37 items · 17 questions · 7 conflicts)
- ✅ Filterable action items by priority (🔴 High / 🟠 Medium / 🟢 Low) and source
- ✅ Zero invented items — `Not specified` used wherever data was absent
- ✅ Conflicts surfaced but **never auto-resolved** — human decides

---

## Core Skill Rules Learned

1. **Never invent** — if data is missing, output `Not specified`
2. **Surface conflicts, don't resolve** — flag both versions, let the human decide
3. **Attribute by speaker** — in multi-person notes, ownership matters
4. **Completed ✓ items ≠ action items** — don't re-add what's already done
5. **Unconfirmed ideas → open questions**, not tasks

---

## Skill Used

`/brain-dump-action-planner` — custom Claude skill (SKILL.md pattern)

Modes supported:
- **Full Breakdown** — summary, action items, risks, open questions, conflicts
- **Transcript Mode** — adds speaker summary + decisions by speaker
- **Merge Mode** — combines multiple sources, flags duplicates and conflicts

---

## Files

```
day-18/
├── README.md                          ← this file
├── dashboard-meeting.html             ← meeting transcript dashboard
├── dashboard-multiformat.html         ← 4-format skill test with scorecard
├── dashboard-review.html              ← consolidated review (all 5 sources)
├── skills/
│   └── brain-dump-action-planner/
│       └── SKILL.md                   ← reusable skill definition
└── sample-inputs/
    ├── meeting-transcript.txt
    ├── brain-dump.txt
    ├── bullet-notes.txt
    ├── voice-memo.txt
    └── whatsapp-chat.txt
```

---

## 8 Key Learnings

1. A **skill** is a reusable Claude instruction set — write it once in `SKILL.md` and invoke it on any input without re-explaining the task each time.
2. **Format-agnostic parsing** is possible — the same skill handled 5 completely different note types with consistent output quality.
3. **Never invent missing information** — `Not specified` is always correct when data is absent. This is the most important rule for trust in AI-generated summaries.
4. **Conflicts must be surfaced, never silently resolved** — if two sources disagree, flag both. Resolution is the human's job.
5. **Speaker attribution is critical** — who said what matters as much as what was said, especially for action item ownership.
6. **Priority badges** (🔴/🟠/🟢) make action items scannable — humans process urgency signals faster than reading sentences.
7. **Cross-source consolidation reveals patterns** invisible in individual notes — the same issue appearing in two formats signals higher urgency.
8. **Interactive HTML dashboards with JS filtering** are far more useful than static lists when dealing with 30+ items.

---

## Connection to Career Goals (10+ LPA)

| Domain | How It Applies |
|---|---|
| Data Analyst | Extracting signal from unstructured sources (notes, Slack, emails) is a core DA workflow |
| Product Manager | Action item extraction with owner + deadline mirrors post-sprint reviews |
| Software Engineer | Building filterable dashboards from scratch shows frontend + data wrangling ability |

Targeted companies: Razorpay · Groww · CRED · Zepto · Atlassian

---

## Progress

```
Day 18 of 60 — 30% complete
████████░░░░░░░░░░░░░░░░░░░░░░  18/60
```

---

*Part of the ABTalks 60-Day Claude AI Mastery Challenge*
*Building in public · GitHub: [sidharth0018](https://github.com/sidharth0018)*

`#ABTalks60Days` `#ClaudeAI` `#PromptEngineering` `#DataAnalytics` `#BuildInPublic`
