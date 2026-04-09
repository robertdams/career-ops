---
name: career-ops-patterns
description: Analyze rejection patterns and improve targeting with data-driven insights
user-invocable: true
---

# career-ops patterns -- Rejection Pattern Detector

Analyze all tracked applications to find patterns and surface actionable insights.

## Execution

Read and execute the full instructions in `modes/patterns.md`:

1. Run `node analyze-patterns.mjs` and parse JSON output
2. Generate report with: funnel, score vs outcome, archetype performance, blockers, remote policy patterns, tech stack gaps, recommendations
3. Save to `reports/pattern-analysis-{YYYY-MM-DD}.md`
4. Present summary and offer to apply recommendations

Requires minimum 5 entries with status beyond "Evaluated".
