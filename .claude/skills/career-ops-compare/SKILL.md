---
name: career-ops-compare
description: Compare and rank multiple job offers with weighted scoring matrix
user-invocable: true
argument-hint: offers
---

# career-ops compare -- Multi-Offer Comparison

Score and rank multiple offers across 10 weighted dimensions.

## Setup

1. Read `modes/_shared.md` for scoring system
2. Read `modes/_profile.md` for user targets and archetypes
3. Read `cv.md` and `config/profile.yml` for candidate context

## Input

`{{offers}}` — Offers to compare. Can be: pasted JD text, URLs, or references to existing tracker entries.

## Execution

Read and execute the full instructions in `modes/ofertas.md`. Produces a scoring matrix (10 dimensions) with weighted totals and a final ranking with time-to-offer considerations.
