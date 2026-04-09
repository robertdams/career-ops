---
name: career-ops-pdf
description: Generate an ATS-optimized CV/PDF tailored to a specific job description
user-invocable: true
argument-hint: jd_or_url
---

# career-ops pdf -- ATS-Optimized CV Generation

Generate a keyword-injected, ATS-optimized PDF CV tailored to a specific job description.

## Setup

1. Read `modes/_shared.md` for global rules and tools config
2. Read `modes/_profile.md` for user archetypes and narrative
3. Read `cv.md` for the candidate's CV
4. Read `config/profile.yml` for candidate identity (name, email, links)
5. Read `templates/cv-template.html` for the HTML template

## Input

`{{jd_or_url}}` — JD text or URL. If not provided, ask the user for the JD.

## Execution

Read and execute the full instructions in `modes/pdf.md`. That file defines the full pipeline from keyword extraction through HTML generation to PDF output.

## Output

- PDF saved to `output/cv-candidate-{company}-{YYYY-MM-DD}.pdf`
- Tracker updated (PDF column set to check mark)
