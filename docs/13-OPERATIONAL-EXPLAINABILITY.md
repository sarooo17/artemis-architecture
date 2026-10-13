# Explainable work without invented reasoning

> **Design thesis:** a runtime should be able to explain what happened, what evidence mattered, and what remains unresolved—without claiming to reproduce hidden model reasoning.

Traditional agent traces can be noisy lists of tool calls. For consequential business work, people need an explanation at the right level of abstraction.

## Several views of the same work

A business user may need to know that a report was verified or that an approval is pending. Someone investigating an incorrect result may need to understand which records were considered and why a step was retried. An administrator may need a more detailed operational history.

These views should arise from **recorded operations, evidence and decisions**, not from prompting a model to improvise a plausible retrospective story.

## What matters

A meaningful work record can distinguish:

- The action that was proposed or attempted.
- The authoritative boundaries it crossed.
- Evidence and references supporting an outcome.
- Work waiting on a person or future event.
- Revisions, partial outcomes and unresolved conflicts.
- The difference between model-derived interpretations and verified world state.

## Why correctness and explainability interact

Suppose a reconciliation concludes that a payment was recorded. A useful explanation should point to the verified business observation or clearly mark that the conclusion is still unverified.

A persuasive narrative without adequate evidence is not operational explainability.

This also influences UI design: the conversational layer, execution status and artifacts should make relevant state visible without exposing internal prompt packages, sensitive policies or private chain-of-thought.

**Status:** execution tracing, verification and evidence foundations exist. The integrated multi-level causal inspection experience is a vNext target. See [Status](STATUS.md).
