---
name: career-ops-apply
description: Live application assistant -- read forms and generate personalized answers
user-invocable: true
argument-hint: company_or_url
---

# career-ops apply -- Application Assistant

Interactive mode for filling application forms. Reads the form, loads prior evaluation context, and generates personalized answers for copy-paste.

## Setup

1. Read `modes/_shared.md` for global rules and tone guidelines
2. Read `modes/_profile.md` for user narrative and framing
3. Read `cv.md` and `config/profile.yml` for candidate data
4. Search `reports/` for existing evaluation of the target company

## Input

`{{company_or_url}}` — Company name, role, or URL of the application form.

## Execution

Read and execute the full instructions in `modes/apply.md`. Workflow:
1. Detect the offer (Playwright snapshot or user-provided screenshot/text)
2. Match against existing reports
3. Detect form questions
4. Generate personalized answers with "I'm choosing you" tone
5. Present formatted for copy-paste

## Post-Apply

If user confirms submission: update status in `data/applications.md` to "Applied".
