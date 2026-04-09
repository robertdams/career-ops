---
name: career-ops-scan
description: Scan job portals for new offers (Greenhouse, Ashby, Lever, company pages)
user-invocable: true
---

# career-ops scan -- Portal Scanner

Scan configured job portals, filter by title relevance, and add new offers to the pipeline.

## Setup

1. Read `modes/_shared.md` for global rules and tools config
2. Read `modes/_profile.md` for user context
3. Read `portals.yml` for search queries and tracked companies
4. Read `data/scan-history.tsv` for previously seen URLs
5. Read `data/applications.md` and `data/pipeline.md` for dedup

## Execution Strategy

This is a heavy task. Launch as a subagent to preserve main context:

```
Agent(
    subagent_type="general-purpose",
    prompt="[content of modes/_shared.md]\n\n[content of modes/scan.md]\n\n[portals.yml config]",
    run_in_background=True,
    description="career-ops scan"
)
```

Read and execute the full instructions in `modes/scan.md`. Three discovery levels:
1. Playwright direct navigation to `careers_url` (primary)
2. Greenhouse API JSON (complementary)
3. WebSearch with `site:` filters (broad discovery)

## Output

- New offers added to `data/pipeline.md`
- All URLs logged to `data/scan-history.tsv`
- Summary with counts: found, filtered, duplicated, new
