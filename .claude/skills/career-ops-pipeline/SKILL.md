---
name: career-ops-pipeline
description: Process pending URLs from the pipeline inbox (data/pipeline.md)
user-invocable: true
---

# career-ops pipeline -- Process Pending URLs

Process all pending URLs accumulated in `data/pipeline.md` through the full auto-pipeline.

## Setup

1. Read `modes/_shared.md` for global rules
2. Read `modes/_profile.md` for user context
3. Read `data/pipeline.md` for pending items
4. Run `node cv-sync-check.mjs` before processing

## Execution

Read and execute the full instructions in `modes/pipeline.md`. For each `- [ ]` item:
1. Extract JD (Playwright > WebFetch > WebSearch)
2. Run full auto-pipeline (evaluate + report + PDF + tracker)
3. Move from "Pendientes" to "Procesadas"

If 3+ URLs pending, launch parallel agents for speed.

## Output

- Reports in `reports/`
- PDFs in `output/`
- Tracker additions merged via `node merge-tracker.mjs`
- Summary table of all processed offers
