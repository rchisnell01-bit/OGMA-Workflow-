# Operating rules, scope, and evidence

This is an adaptable **operating procedure**, not a new application or a guarantee that the AI providers are linked.

## Routing: the smallest capable team

| Situation | Default |
| --- | --- |
| Short straightforward task | Manager does it directly |
| A specialist provides a meaningful advantage | Assign exactly one bounded task |
| Two independent deliverables with no conflicting ownership | Consider parallel work **only if you can actually activate and check both workers** |
| Multiple dependent deliverables | Sequence assignments; the manager owns integration and final QA |
| Expensive, uncertain, or sensitive work | Reduce scope, seek approval, or stop |

**Count coordination as work.** A second agent is not automatically a quality improvement. Token costs, subscriptions, copying effort, and human rescue matter. Mark inaccessible numbers `UNKNOWN`, not zero.

## State vocabulary

| State | Minimum evidence required |
| --- | --- |
| `DRAFTED` | Assignment exists |
| `ASSIGNED_AWAITING_ACK` | Assignment offered or dispatched; no verified worker acceptance |
| `IN_PROGRESS` | Actual worker acknowledged and began the task |
| `DELIVERED` | Actual worker returned a deliverable or artifact |
| `REVIEWED` | Manager inspected deliverable and evidence against the request |
| `VERIFIED_DONE` | Required checks substantiate the claimed result |
| `BLOCKED` | Essential input, tool, access, evidence, or approval is unavailable |

Do not skip from `ASSIGNED_AWAITING_ACK` to `VERIFIED_DONE` based only on a board note. It is normal for a fast worker to acknowledge and return the work in a single reply; that still requires a separate managerial review before verification.

## Required assignment contract

Every specialist brief must contain: stable task ID; exact deliverable; source material the worker can actually access; boundaries and prohibited actions; acceptance criteria; result/evidence format; current authorization. Use [the template](../templates/assignment.md).

**One action, one accountable owner.** Two agents should not edit the same file or send to the same customer simultaneously. A shared document is a log, not proof that an agent has executed a task. Read back important writes when real connected tools are used.

## Verification standard

- Distinguish **observed evidence**, **worker-reported claims**, and **unknowns**.
- For factual claims, compare against authoritative provided sources or independently fetched sources if available.
- For code, run applicable tests. For designs, inspect the actual output. For messages or purchases, check real receipts or system state after an approved action.
- Do not turn example text into measured benchmarks; do not claim all models have been validated.
- If the source or tool is not accessible, report `UNVERIFIABLE` or `BLOCKED` rather than declaring success.

## Approval gates

The human must explicitly approve sending customer messages, changing production, publishing, installing paid tools, incurring charges, deleting records, sharing confidential material, and similar consequential actions. A general approval to research or draft does not also authorize execution. Maintain any more restrictive user rules.

## Recovering from errors

1. Before retrying a possible external action, check whether it already happened.
2. If delivery status is ambiguous, mark `BLOCKED` or hold for status confirmation; don't duplicate a send or purchase.
3. Correct the smallest actual defect. Do not reassign completed work or silently change the workflow.
4. Report the evidence, unresolved question, and next accountable person.

## Modes

**Manual (supported in v0.1):** Two AI chats, a human passing one bounded packet/result. No shared memory is assumed.

**Connected (user-built extension):** Users with a supported connector or orchestrator may adapt the same contract for direct execution, but must verify supported permissions, acknowledgment, results, privacy, and costs. No connector integration ships in this release.
