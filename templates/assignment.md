# Worker assignment template

Copy, fill in only the fields needed, and send **one** packet to **one** clearly owned worker. Never include secrets unless the specific approved task truly requires them and a safe channel exists.

```text
ASSIGNMENT PACKET
TASK_ID: [stable unique ID]
ASSIGNED_TO: [worker / chosen model]
OBJECTIVE: [one measurable deliverable]
SOURCE_OF_TRUTH: [specific, safe facts or files the worker can actually access]
INPUTS: [minimum relevant context]
OUT_OF_SCOPE: [what not to do]
AUTHORIZED_ACTIONS: [e.g. read, analyze, draft; no sends or writes unless specifically approved]
ACCEPTANCE_CHECKS: [what the manager will inspect]
RETURN_FORMAT: ACK <TASK_ID>; output; result status; evidence; limitations; external actions; known or UNKNOWN cost

CURRENT_MANAGER_STATUS: ASSIGNED_AWAITING_ACK
```

If you manually relay this packet, do not claim it was automatically sent. When no worker responds, its status stays `ASSIGNED_AWAITING_ACK`, not `IN_PROGRESS`.
