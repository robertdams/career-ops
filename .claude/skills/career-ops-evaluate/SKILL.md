---
name: career-ops-evaluate
description: Evaluate a job offer with A-F scoring (archetype detection, CV match, comp research, interview prep)
user-invocable: true
argument-hint: jd_or_url
---

# career-ops evaluate -- Full A-F Evaluation

Evaluate a job offer pasted as text or URL. Produces a 6-block report with scoring.

## Setup

1. Read `modes/_shared.md` for scoring system, global rules, and tools config
2. Read `modes/_profile.md` for user archetypes, narrative, and negotiation scripts
3. Read `cv.md` for the candidate's CV
4. Read `config/profile.yml` for candidate identity and targets
5. If `article-digest.md` exists, read it for detailed proof points
6. **First evaluation of each session:** Run `node cv-sync-check.mjs`. If warnings, notify user.

## Input

`{{jd_or_url}}` — Either pasted JD text or a URL to a job posting.

If URL: extract JD via Playwright (`browser_navigate` + `browser_snapshot`), fallback to WebFetch, then WebSearch.
If text: use directly.

## Execution

Read and execute the full instructions in `modes/oferta.md`. That file defines:

- Step 0: Archetype detection
- Block A: Role summary
- Block B: CV match (with gap analysis)
- Block C: Level and strategy
- Block D: Comp and demand (WebSearch)
- Block E: Personalization plan
- Block F: Interview prep (STAR+R stories)
- Post-evaluation: Save report to `reports/`, register in tracker

## Output

- Report saved to `reports/{###}-{company-slug}-{YYYY-MM-DD}.md`
- Tracker entry written to `batch/tracker-additions/{num}-{company-slug}.tsv`
- Run `node merge-tracker.mjs` after writing tracker addition
