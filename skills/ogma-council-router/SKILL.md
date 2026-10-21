---
name: ogma-council-router
description: Screen every incoming task for whether an independent multi-model council would materially improve the decision. Use the existing OGMA coordinator, approval gates and evidence rules. A real council run requires an installed, verified runtime.
---

# OGMA Council Router

This is a portable routing skill and policy, **not** the council runtime. It is meant for OGMA-compatible Codex/Claude/other agents when copied into a supported skill location. Read [the integration guide](../../docs/llm-council.md) for setup and verification.

## Screen EVERY incoming question or task

Assess: complexity, stakes, uncertainty, reversibility, evidence quality, expected benefit of independent review, urgency, usage cost, and whether actual external models are accessible.

1. **DIRECT** — simple factual questions, routine replies, low-risk edits, straightforward actions: answer or execute with one agent; do not invoke a council.
2. **FOCUSED REVIEW** — an important claim, uncertain business choice or design/coding change: one independent specialist if its expected value exceeds coordination cost.
3. **FULL COUNCIL** — consequential, hard-to-reverse, ambiguous, technical/security, strategic or explicitly council-requested decisions: independent models, adversarial critique, synthesis and manager verification. Use only *actually available* distinct models.
4. **BLOCKED/DEGRADED** — no verified runtime, provider failure, credential/permission issue or budget cap: disclose it, work within existing permissions, never invent model votes.

If the user explicitly requests that all decisions be considered for council review, satisfy that by screening every request. Do not incur repeated multi-provider work for every trivial answer unless explicitly required and authorized with its usage consequences.

## Chair and boundaries

- OpenAI/Joffrey (or the current actual OGMA coordinator) owns routing, final review and handoff. Council input is advice, **not authorization**.
- Preserve a single existing source of truth and assigned task owners. Do not create a second board, reopen finished work, change provider/model settings, or spend money to fit a council recipe.
- Use providers **codex, gemini-cli, claude** only after local login + compatibility + real generation have been verified. There is no verified Meta CLI in this selected package; Meta is optional and must not be fabricated.
- Use the existing shared board to record substantive council decisions and evidence, not each routine screening.
- Do not share customer/private information with another provider unless covered by the user's authorization and data-sharing controls.

## Live council verification

The selected engine is [sherifkozman/the-llm-council](https://github.com/sherifkozman/the-llm-council), version 0.8.4+; use its own skill and portable invocation contract. A copied instruction file is not an installed/working runtime.

Before any real council run: check exact installed binary/version, provider auth/readiness, Codex version allowlist, selected models and cost route. Explicitly disable unexpected API providers by supplying verified local CLI providers. Use unique task/result files and inspect execution_status, provider drafts, critique, degradation and source coverage; never take exit status alone as verification.

For substantial decisions, return: **recommendation; strongest disagreement; evidence; risks; next permitted action; council execution evidence (or not run)**. Avoid verbose multi-agent transcripts when the answer can be short.
