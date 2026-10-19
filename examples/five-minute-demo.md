# Five-minute demonstration: one worker, one manager

This exercise is **fictional** and requires **no browsing, customer contact, API key, or spending**. It tests the handoff, evidence check, and correction loop—not autonomous cross-model messaging.

## 1. Start two chats

- In Chat A, paste [manager.md](../prompts/manager.md) (the full prompt inside the text block).
- In Chat B, paste [worker.md](../prompts/worker.md) (the full prompt inside the text block).

## 2. Give this exact task to Chat A

```text
Practice a single cross-model handoff for this demonstration. Do not do the writing yourself. Delegate the draft to the worker chat, then verify it yourself when I bring the response back. No external actions are authorized.

FICTIONAL BUSINESS: Cedar Street Bicycle Repair.
ONLY APPROVED FACTS:
- Offers basic bicycle tune-ups, flat tire fixes, and brake adjustments.
- Works by appointment.
- Customers can request an appointment through a website contact form.
- There is no approved information about pricing, business hours, locations, or appointment availability.

REQUEST: Three distinct one-sentence service blurbs (20 words maximum each) and a short appointment call-to-action (15 words maximum). Don't invent facts, discounts, guarantees, pricing, hours, service areas, or availability. Assign task ID DEMO-001. Give me a compact assignment packet to paste into Chat B.
```

**Expected:** Chat A produces a clearly marked `ASSIGNMENT PACKET`. It should not claim Chat B is already working or that the draft is complete. It should show `ASSIGNED_AWAITING_ACK` until Chat B replies.

## 3. Hand it to Chat B

Copy the assignment packet produced in Chat A into Chat B. Chat B should acknowledge `DEMO-001`, write the requested blurbs, and report `DELIVERED`, with evidence limited to the provided facts. **You are the messenger in this starter version.**

## 4. Return the result to Chat A

Paste Chat B's whole reply back into Chat A with:

```text
Here is the actual worker reply for DEMO-001. Check every service and the call-to-action against the approved facts and word limits. Report what you checked and assign the correct status. Do not publish or send anything.
```

A defensible manager outcome is `VERIFIED_DONE` **only when** every factual and formatting check passes. If the reply adds an unsupported statement, the manager should identify it, request or make the smallest authorized correction, and re-check before completion.

## 5. Optional error-recovery exercise

Pretend a careless worker wrote: **"Same-day flat repairs from $25."** That statement is **not supported** by the approved facts (no price or availability was supplied).

Tell Chat A: `Check this proposed line against the approved facts: Same-day flat repairs from $25.` The manager should **reject or correct** it, not repeat it as fact.

## What this does—and does not—prove

This tests whether your chats can exchange bounded instructions **through you** and whether the manager follows verification rules. It does **not** prove fully automated communication, live connectors, independent source checking, measured cost savings, or reliability across all AI providers.
