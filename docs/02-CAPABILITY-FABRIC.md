# A compact capability fabric

> **Design thesis:** the model should discover what it needs through a small, governed interface rather than receive an enormous, static catalog of executable tools.

## The problem with an expanding tool list

Enterprise work spans records, workflows, documents, internal systems, and external providers. Adding one model-visible tool for each possible operation expands both the context surface and the opportunity for an agent to choose incorrectly.

Artemis treats a **capability** as a semantic operation: something meaningful the environment can do. A capability is not necessarily the name of an endpoint, an MCP tool, or an internal function.

The underlying provider and protocol may change while the semantic operation remains recognizable to the system.

## Compact outside, rich inside

The architectural pattern is a **small public-facing interaction surface** backed by a richer capability fabric:

- **Discover:** find candidate operations relevant to a goal.
- **Inspect:** obtain the description and constraints needed for a candidate.
- **Invoke:** request a permitted operation with structured input.
- **Retrieve:** obtain the result or an appropriate reference to it.

These are conceptual functions, **not a promise of a public API**.

The model does not need every business schema in its initial context. Nor does discovering an operation imply permission to execute it.

## Capability access is contextual

For a procurement investigation, the effective environment may expose supplier and purchasing records while withholding unrelated personnel operations. If work later needs a different capability, the environment may be expanded through a governed request rather than assuming a universal all-tools agent.

The design separates:

1. **Meaning:** what operation the task needs.
2. **Availability:** which connected systems can support it.
3. **Access:** whether the current actor and task are permitted to use it.
4. **Execution:** where and how it is actually performed.
5. **Evidence:** what the operation returned and what can be concluded from it.

The authorization boundary matters at both discovery and invocation. A capability that cannot be used must not become authorized merely because it was found or described.

## Why this matters beyond token cost

A compact surface is not just context optimization. It helps avoid binding agent behavior to one provider's tool naming, limits accidental exposure of irrelevant operations, and makes task-specific environments easier to reason about.

It also creates a trade-off: discovery can be incomplete or ambiguous. The runtime therefore needs ways to request missing capabilities and make that limitation visible instead of blindly inventing an answer.

## What stays unpublished

This note deliberately omits registry internals, ranking mechanics, access-control matrices, provider-specific adapters, tool schemas, and production limits.

**Status:** Artemis already has capability abstraction and compact discovery/execution foundations. The target model refines how capability access is assembled per assignment. [Status](STATUS.md).
