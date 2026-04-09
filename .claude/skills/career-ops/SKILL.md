---
name: career-ops
description: AI job search command center -- route to sub-skills or auto-detect JD for full pipeline
user-invocable: true
argument-hint: mode
---

# career-ops -- Router

## Mode Routing

Determine the mode from `{{mode}}`:

| Input | Skill to invoke |
|-------|-----------------|
| (empty / no args) | Show discovery menu below |
| JD text or URL (no sub-command) | **auto-pipeline** (see below) |
| `evaluate` or `oferta` | `/career-ops-evaluate` |
| `compare` or `ofertas` | `/career-ops-compare` |
| `contact` or `contacto` | `/career-ops-contact` |
| `deep` | `/career-ops-deep` |
| `pdf` | `/career-ops-pdf` |
| `training` | `/career-ops-training` |
| `project` | `/career-ops-project` |
| `tracker` | `/career-ops-tracker` |
| `pipeline` | `/career-ops-pipeline` |
| `apply` | `/career-ops-apply` |
| `scan` | `/career-ops-scan` |
| `batch` | `/career-ops-batch` |
| `patterns` | `/career-ops-patterns` |
| `interview` or `interview-prep` | `/career-ops-interview` |

**Auto-pipeline detection:** If `{{mode}}` is not a known sub-command AND contains JD text (keywords: "responsibilities", "requirements", "qualifications", "about the role", "we're looking for", company name + role) or a URL to a JD, execute **auto-pipeline**.

If `{{mode}}` is not a sub-command AND doesn't look like a JD, show discovery.

---

## Auto-Pipeline (JD detected)

When a JD or URL is detected, run the full pipeline in sequence:

1. Read `modes/_shared.md`, `modes/_profile.md`, `cv.md`, `config/profile.yml`
2. Read `modes/auto-pipeline.md` for the full step-by-step instructions
3. Execute: Extract JD -> Evaluate A-F -> Save Report -> Generate PDF -> Draft Answers (if score >= 4.5) -> Update Tracker

---

## Discovery Mode (no arguments)

Show this menu:

```
career-ops -- Command Center

Available commands:
  /career-ops {JD}          -> AUTO-PIPELINE: evaluate + report + PDF + tracker
  /career-ops evaluate      -> Evaluation only A-F (no auto PDF)
  /career-ops compare       -> Compare and rank multiple offers
  /career-ops pdf           -> PDF only, ATS-optimized CV
  /career-ops contact       -> LinkedIn: find contacts + draft message
  /career-ops deep          -> Deep company research
  /career-ops interview     -> Company-specific interview prep
  /career-ops training      -> Evaluate course/cert
  /career-ops project       -> Evaluate portfolio project idea
  /career-ops tracker       -> Application status overview
  /career-ops apply         -> Live application assistant
  /career-ops scan          -> Scan portals for new offers
  /career-ops pipeline      -> Process pending URLs from inbox
  /career-ops batch         -> Batch processing with parallel workers
  /career-ops patterns      -> Analyze rejection patterns

Or use individual commands directly:
  /career-ops-evaluate, /career-ops-pdf, /career-ops-scan, etc.

Inbox: add URLs to data/pipeline.md -> /career-ops pipeline
Or paste a JD directly to run the full pipeline.
```
