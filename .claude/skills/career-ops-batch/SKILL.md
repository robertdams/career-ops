---
name: career-ops-batch
description: Batch evaluate multiple job offers in parallel with sub-agent workers
user-invocable: true
---

# career-ops batch -- Batch Processing

Process multiple job offers in parallel using `claude -p` workers or Agent subagents.

## Setup

1. Read `modes/_shared.md` for global rules
2. Read `modes/_profile.md` for user context
3. Read `batch/batch-prompt.md` for worker prompt template
4. Read `batch/batch-state.tsv` if it exists (resumability)

## Execution

Read and execute the full instructions in `modes/batch.md`. Two modes:

- **Mode A: Conductor --chrome** — Navigate portals in Chrome, extract JDs, dispatch workers
- **Mode B: Script standalone** — Run `batch/batch-runner.sh` on pre-collected URLs

Each worker produces: report `.md`, PDF, tracker line in `batch/tracker-additions/`.

## Post-Processing

After all workers complete, run `node merge-tracker.mjs` to merge tracker additions into `data/applications.md`.
