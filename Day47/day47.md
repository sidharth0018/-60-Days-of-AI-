# Day 46 — Content Intelligence Studio

**Challenge:** ABTalks 60-Day Claude AI Mastery Challenge
**Focus area:** Multi-agent AI review pipelines + LLM output reliability

## The problem

I wanted to build a tool that could actually critique my own content the way a small team of specialists would — a strategist, a designer, a copywriter, a psychologist, and an editor — instead of one AI giving one generic opinion. I also wanted it to work on **images**, since most of my LinkedIn content is screenshots, carousels, or visual posts.

## What I built

**Content Intelligence Studio** — a single-page HTML app that:

- Interviews the user first (content type → platform → goal → upload type → review strictness), using tappable MCQ-style options instead of a wall of text fields
- Dynamically builds a **different reviewer team** depending on the answers (a job-seeker's LinkedIn post gets a Recruiter Lens; a growth-focused post gets a Growth Analyst instead)
- Sends the uploaded image directly to Claude as a base64 image block so it's genuinely analyzing what's on screen — colors, layout, text in the image, cropping — not guessing from a caption
- Runs each reviewer as its own Claude API call with a dedicated system prompt and tone setting (gentle / balanced / brutal)
- Feeds all reviewer notes into a final "Editor-in-Chief" call that produces one structured report: scores, strengths, weaknesses, missed opportunities, two full rewrites, alternate hooks, a publishing checklist, before/after framing, and a clearly-labeled AI performance estimate
- Displays everything in a premium, animated, dark/light-mode dashboard with a live "reviewer pipeline" activity log while the calls run

## Key technical decision: no JSON

Earlier builds in this challenge occasionally broke when the model's JSON response had a stray character, an extra comma, or unescaped quotes inside a rewritten caption — producing errors like `Unexpected token` or `expected '{' or '('`. For this build I deliberately avoided JSON entirely:

- The synthesis prompt specifies an exact **plain-text section protocol** (`OVERALL_SCORE:`, `CATEGORY_SCORES:`, `STRENGTHS:`, `REWRITE_1:`, `DEEPER_PROMPTS:`, etc.)
- The frontend parses this with simple regex + line-splitting instead of `JSON.parse`
- This is far more tolerant of natural variation in how the model writes long-form text (rewrites can contain quotes, line breaks, emoji — anything — without breaking the parser)

## Result

A working, zero-dependency HTML app that turns one screenshot into a full agency-style content audit in under a minute, with every word of feedback generated live by Claude — no canned scoring, no placeholder text.

## Next steps

- Add an ATS/keyword-density reviewer specifically for job-seeking use cases
- Support multi-image carousel review
- Add a "compare two versions" mode to A/B two drafts against each other
