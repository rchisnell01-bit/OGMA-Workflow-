# Worker response template

```text
ACK: [TASK_ID]
TASK_ID: [same exact ID]
RESULT_STATUS: DELIVERED / BLOCKED
DELIVERABLE: [specific work or exact artifact reference]
EVIDENCE: [actual sources used and checks performed; separate facts from reported claims]
LIMITATIONS: [unknowns, unavailable tools, untested features]
EXTERNAL_ACTIONS: [none, or exactly what was explicitly authorized and verified]
COST: [measured amount and units, or UNKNOWN]
NEXT_ACTION: [smallest necessary follow-up; do not self-assign more work]
```

Only the manager can upgrade a returned deliverable to `REVIEWED` or `VERIFIED_DONE` after checking it. Do not invent links, source access, receipts, or costs.
