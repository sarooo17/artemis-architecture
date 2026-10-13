# Continuation, not an endless prompt loop

> **Design thesis:** the durable work engine, rather than the model's next token, should own whether work proceeds, waits, changes strategy, or ends.

## One goal, different kinds of next step

A goal may need a calculation, a capability invocation, a semantic decision, open-ended reasoning, human approval, an external event, or a verification step.

Not all these steps require the same kind of intelligence.

Artemis vNext frames continuation around a small set of conceptual operations:

- **Compute:** perform a calculation, bounded semantic decision, or deeper reasoning.
- **Act:** interact with an authorized system.
- **Verify:** inspect whether a condition or effect actually holds.
- **Delegate:** hand independent work to a separate durable unit where justified.
- **Ask / Wait:** pause for human input or a future condition.
- **Complete / Fail:** reach an explicit terminal outcome.

This is a public *semantic description*, not an executable contract.

## Multi-agent without agent proliferation

An independently durable subtask can justify a child Execution: it may have separate progress, evidence, retries, or external dependencies.

A quick specialist opinion generally does not. The architecture distinguishes a useful reasoning contribution from a new independently scheduled task.

That distinction matters for cost, clarity, and recovery.

## Resumption is not simply "run the prompt again"

When work resumes after a delay, the world may have changed: access may have been revoked, a record amended, or a prior assumption invalidated.

A sound continuation must re-evaluate what is still true and permitted. A persisted intention is not permanent permission.

## What success means

A task should not transition to "done" merely because a model states that it has succeeded. The requested postconditions, and the evidence appropriate to them, determine completion.

Likewise, a partial result should be presented as partial work rather than rewritten into a success-shaped message.

**Status:** continuity, recovery, and verification primitives exist in the current architecture; the unified runtime-owned continuation semantics remain a vNext design and implementation stream. [Status](STATUS.md).
