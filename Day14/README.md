# Day 14 — AI JD Red Flag Detector

**ABTalks 60-Day Claude AI Mastery Challenge**

## What I built today
A reusable prompt template that uses Claude as a structured Job Description
analyzer — scoring risk across 5 dimensions and generating a full report with
flags, verdicts, and smart interview questions.

## The prompt pattern
**Role + Input schema + Output format = structured, reusable analysis**

This is one of the most powerful patterns in prompt engineering. By defining:
- What role Claude plays (Red Flag Detector)
- What the input is (JD + Company info)
- What the output must look like (score, table, verdict, questions)

...you get consistent, high-quality analysis on any JD in under 2 minutes.

## Files in this folder
| File | Description |
|------|-------------|
| `prompt-template.md` | Reusable prompt — works for any job description |
| `output-report.md` | Full analysis output for Deloitte Analyst, Analytics role |
| `deloitte-jd.png` | Original JD screenshot used as input |

## What I learned
- Decision-support prompting: using AI for structured risk analysis, not just text generation
- The Role + Input + Output prompt pattern produces reusable, consistent results
- Same pattern applies beyond job hunting — vendor contracts, project briefs, client proposals

## How to reuse this template
1. Open `prompt-template.md`
2. Paste any job description where it says `[paste JD here]`
3. Add basic company background where it says `[paste company background here]`
4. Run in Claude — get your risk report in seconds

## Day 14 concept
**Decision-support prompting** — giving Claude a defined role, structured input,
and an exact output schema to produce analytical reports that help you make
better decisions faster.
