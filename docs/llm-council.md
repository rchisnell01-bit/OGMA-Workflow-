# LLM Council — optional integration with OGMA

**Status: Policy integrated into OGMA. External multi-model execution is NOT enabled by this repository change.** Existing OGMA v0.1 manual operation still works unchanged.

## Choice and purpose

Use [Sherif Kozman's The LLM Council](https://github.com/sherifkozman/the-llm-council) (MIT; skill + local `council` runtime) as the council engine. It supports independent drafts, adversarial critique, synthesis, review/research/plan modes, and authenticated local Codex, Gemini and Claude command-line tools.

The universal policy is: **screen every question; do not convene every time**. Escalate to independently verified multi-model collaboration for meaningful uncertainty, risk or consequential decisions, or an explicit council request. Maintain the smallest effective team for daily operations.

## Where it fits

- **Current ChatGPT conversation:** can apply the screening rule, but it does not install external software into ChatGPT or make other AI chats reachable. Do not claim a council has been convened without real outputs.
- **Joffrey:** coordination remains with Joffrey; on next active board read apply this policy to new tasks. A board note is not an activation receipt. Do not create a new task tracker.
- **Codex / local development:** install the selected engine and skill in the machine/runtime that actually launches Codex, after environment checks below. Installation inside an unrelated container will not install it on a user's Windows machine.
- **Other connected agents:** use their existing handoff channels. Only report independent consultation if that agent really ran and returned a result.
- **OGMA public starter:** this is optional guidance. It remains a manual copy/paste starter unless a user independently sets up and verifies a connected implementation.

## Preflight — do not assume access

1. On the intended Windows/WSL host, check Python 3.10–3.12 and the availability/authentication of `codex`, `gemini`, and `claude` CLIs. Check the actual `codex --version`. As of the documented upstream skill v0.8.4, Codex admission is restricted to **0.149.1 / 0.153.3 / 0.160.1**; an unknown build is a blocker, not an invitation to bypass checks.
2. If the host is compatible and installing is authorized, install a pinned supported `the-llm-council` version into the actual intended environment; consult the upstream [skill instructions](https://github.com/sherifkozman/the-llm-council/blob/main/skills/council/SKILL.md) and [portable invocation contract](https://github.com/sherifkozman/the-llm-council/blob/main/skills/council/references/invocation-contract.md). **Do not add** API keys, OpenRouter or paid services by default.
3. Install/copy upstream `skills/council/` into the runtime's discovered skill directory. The OGMA router `skills/ogma-council-router/` is a separate routing instruction, and likewise must be copied into the actual agent's supported location. A GitHub commit is not an account-wide ChatGPT skill installation.
4. Run `council version`, `council doctor` and supported `council doctor --deep --provider codex --provider gemini-cli --provider claude` (one per provider as appropriate). **Deep probes consume usage** and must be authorized by the existing cost limits. A basic doctor check is not proof of generation capability.
5. Perform ONE bounded actual three-provider council run using explicitly approved local CLI providers, explicit verified model IDs in matching order and non-sensitive test input. Use unique output file and read the final JSON and diagnostics after process termination. Only say "council working" if independent drafts, critique and synthesis actually ran and source coverage/phase failures were reviewed.
6. If any provider or version is blocked, stop that portion, preserve the working team, and report the exact blocker. Do not substitute a single-model role play for three independent AI responses.

## Dispatch rules

| Intake | Default |
| --- | --- |
| Straightforward question or routine draft | Direct answer. Screened, no council execution. |
| Important claim, meaningful ambiguity, customer-facing strategy | Existing specialist or focused independent review when accessible. |
| System architecture, high-risk edit, substantial financial/business decision, consequential research or explicitly requested council | Council if available and justified; report dissent and evidence. |
| Deadline, usage cap or missing access | Direct/partial answer with clear uncertainty or BLOCKED. |

Do not re-review identical settled facts; reuse verified council results until the actual evidence or decision materially changes. Do not schedule continuous councils, exhaust plan allowances or auto-invoke all providers on every question.

**Privacy / approval:** Preserve existing human approvals for customer sends, purchases, publication, account changes, deletion and spending. A council has no authority to expand its permissions. Its conclusions are not evidence that an external action happened.

## Result record — existing board only

For material councils, save a brief row in the existing handoff board containing: task ID, question, actual provider names / status, main recommendation, meaningful disagreement, source links or artifacts, costs if known, verification status, owner and any user approval needed. Do not log a new row for each simple chat response.

## Activation ledger (initial)

- Routing guidance: added to OGMA repository and Plainwork board for active agents to read.
- Engine package: **NOT INSTALLED/VERIFIED on user's Windows or ChatGPT Work runtime by this change**.
- Provider auth, live council, and Meta participation: **NOT VERIFIED**.
- Account-wide ChatGPT skills, other chat instances, and Joffrey's session: **NOT AUTOMATICALLY MODIFIED**.

Preserve OGMA's current prompts and existing skills. The upstream council is an optional execution adapter, not a replacement for OGMA's manager/worker/approval process.
