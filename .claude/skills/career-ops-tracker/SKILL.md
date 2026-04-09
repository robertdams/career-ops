---
name: career-ops-tracker
description: View and manage application tracker status and statistics
user-invocable: true
---

# career-ops tracker -- Application Status Overview

Display the current state of all tracked applications with statistics.

## Execution

1. Read `data/applications.md`
2. Display the tracker table
3. Show statistics:
   - Total applications
   - Count by status (Evaluated, Applied, Interview, Offer, Rejected, Discarded, SKIP)
   - Average score
   - % with PDF generated
   - % with report generated

If the user asks to update a status, edit the corresponding row in `data/applications.md`.
Use canonical statuses from `templates/states.yml`.
