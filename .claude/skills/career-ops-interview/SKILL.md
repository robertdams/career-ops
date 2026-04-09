---
name: career-ops-interview
description: Company-specific interview prep -- research, questions, story mapping, signals
user-invocable: true
argument-hint: company_and_role
---

# career-ops interview -- Interview Intelligence

Deep interview preparation for a specific company and role.

## Setup

1. Read `cv.md`, `config/profile.yml`, `modes/_profile.md` for candidate context
2. Search `reports/` for existing evaluation
3. Read `interview-prep/story-bank.md` for prepared stories
4. If `article-digest.md` exists, read for proof points

## Input

`{{company_and_role}}` — Company name and role title.

## Execution

Read and execute the full instructions in `modes/interview-prep.md`:
1. Research (Glassdoor, Blind, LeetCode, eng blog, general)
2. Process overview (rounds, difficulty, quirks)
3. Round-by-round breakdown
4. Likely questions (technical, behavioral, role-specific, red flags)
5. Story bank mapping with gap identification
6. Technical prep checklist
7. Company signals (values, vocabulary, things to avoid, questions to ask)

## Output

Report saved to `interview-prep/{company-slug}-{role-slug}.md`
