# Authority is not intelligence. Completion is not a sentence.

> **Design thesis:** the ability to propose an action, permission to perform it, and evidence that it succeeded are three separate things.

## The authority boundary

A model may identify the most plausible next action. That does not mean it has authority to perform it.

A connected system may contain an API credential. That does not mean every task should inherit every action that credential supports.

An uploaded document may contain imperative language. That does not make it a source of runtime policy.

Artemis treats permission, task delegation, user involvement, and operational checks as governed boundaries outside the model's confidence.

## Describing an action is not performing it

A capability may have a contract for preparing, executing or verifying an action without the corresponding operation being enabled in a particular environment. The current ERP-based demonstration should **not** be interpreted as providing unrestricted write access: the implemented ERP interface is primarily read-oriented, and a draft or preview is different from a committed change.

## The verification boundary

Business operations are not complete when a tool call returns a friendly message. A consequential result may need to be confirmed against the system of record or an independent piece of evidence.

Verification is more than a unit test. It asks whether the real-world postcondition is met.

A useful result should distinguish:

- **Observed:** what a source reported.
- **Inferred:** what the system concluded.
- **Authorized:** what was permitted in this context.
- **Verified:** what was checked against an appropriate source.
- **Unresolved:** what still requires information or attention.

## Inspectability without revealing private reasoning

The goal is to explain actions, evidence, status transitions, and blockers from operational records. It is not to reconstruct hidden model chain-of-thought or expose internal prompts.

This becomes more important as work continues over time and multiple people may need to inspect what happened.

## The cost of discipline

Approval and verification boundaries create latency and operational complexity. They are particularly valuable where the system changes business state. Artemis does not assume every low-risk interaction needs the same process.

**Status:** existing guardrails and verification components inform this design; the full end-to-end governance model is being developed further. [Status](STATUS.md).
