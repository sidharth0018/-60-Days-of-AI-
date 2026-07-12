# Day 41 — Resume ATS Keyword Analyzer

**Project:** 60 Day Claude AI Challenge
**Day:** 41

## TL;DR
A Claude-powered CLI tool that compares a resume against a job description and returns a structured ATS-style match report — matched keywords, missing keywords, a match score, and non-fabricated rewrite suggestions. Built to help tailor resumes for Data Analyst / Data Science roles before submission.

## Objective
Applicant Tracking Systems (ATS) commonly filter resumes using keyword and phrase matching before a human ever reviews them. Day 41's goal was to build a lightweight, reproducible tool that uses Claude to:
1. Extract key skills, tools, and qualifications from a job description.
2. Compare them against a candidate's resume text.
3. Return a structured match report: matched keywords, missing keywords, and short, actionable rewrite suggestions.

## Summary of Experiments / Lessons Learned
- Structured JSON output from Claude (via explicit schema instructions) was far more reliable than parsing free-form text — reduced post-processing code by roughly half.
- Splitting the task into two prompts (extract job requirements → compare against resume) produced more accurate matches than a single combined prompt.
- Keeping resume/job description text under ~3,000 tokens combined kept latency low and avoided truncation issues.
- Explicitly instructing the model to avoid inventing skills not present in either document reduced hallucinated keyword matches.

## Reproducible Steps

1. Clone the repository and navigate to the Day 41 folder:
