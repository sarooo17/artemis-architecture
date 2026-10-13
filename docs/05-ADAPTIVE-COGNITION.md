# Adaptive cognition

> **Design thesis:** intelligence should be assigned to the part of a problem that requires it, not spent uniformly on every operation.

## Three different questions

**Is this operation allowed?** That belongs to policy and deterministic constraints.

**Which of a small number of valid interpretations fits best?** That may be handled as a bounded semantic decision.

**What should be done when the solution is not yet known?** That is a better use of open-ended reasoning.

Treating all three as a generic chat-completion request costs more and weakens architectural boundaries.

## A differentiated compute path

Artemis explores a division of responsibility among:

- Deterministic logic for invariant checks, routine transformations, and known operations.
- Constrained decision systems for classification or selection within a defined space.
- General reasoning models for unfamiliar situations, planning, synthesis, and recovery.
- Controlled computational environments when an outcome is better calculated or tested than guessed.

The runtime, not a model's self-assertion, validates proposed changes to context, capabilities and compute resources. **Authority is different:** a stronger model, higher confidence or missing capability cannot create permissions. Any new action scope still needs appropriate delegation, policy and, where required, human approval. Cognitive adaptation cannot bypass these boundaries.

## The more interesting part: knowing what is missing

A poor result may be caused by missing facts, absent capabilities, insufficient expertise, stale evidence, a policy restriction, or genuine reasoning difficulty.

Those are different failure categories. Artemis aims to surface the *type of missing resource*, then address it at the right layer rather than always retrying with a larger model.

## Trade-offs

Bounded decisions can be cheaper and more inspectable, but only when the choice set is genuinely bounded. If the set is incomplete, constraining the model can produce false confidence. The system therefore needs explicit escape paths for open-ended reasoning or human judgment.

**Status:** the current runtime contains adaptive execution foundations. The complete composition of deterministic, bounded, and open reasoning under one continuation policy is a vNext target. [Status](STATUS.md).
