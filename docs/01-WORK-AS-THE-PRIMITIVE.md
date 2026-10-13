# Work as the primitive

> **Design thesis:** a conversation is useful for expressing intent; it is not necessarily the right place to own execution state.

## The mismatch

A conventional assistant receives a request, reasons within a turn, possibly invokes tools, and returns a response. This is appropriate for many questions. It is a poor universal model for business processes that cross systems, people, and days.

Consider "resolve this supplier discrepancy." The response may arrive quickly; the resolution may depend on a supplier reply next week. If the conversation transcript is the only source of task truth, continuity becomes fragile.

Artemis distinguishes three concepts:

- **Conversation:** how a person speaks with the system and changes intent.
- **Execution:** a durable identity for a piece of work, its progress, dependencies, evidence, and outcome.
- **Case:** an optional, longer-lived business concern that can organize multiple Executions over time.

The conversation may initiate, inspect, steer, or cancel work. It does not need to become the work's database or scheduler.

## Why the distinction matters

A user should be able to ask an unrelated question while work continues. A task may wait without keeping an inference loop alive. Several independent tasks may coexist in one workspace, and their histories should remain understandable without searching across chat threads.

This does **not** imply that every click or lookup becomes a durable Execution. Lightweight interactions should remain lightweight. Durability is useful when work has meaningful lifecycle, dependencies, external effects, or recovery needs.

## A conceptual example

A user asks for an invoice anomaly review. One Execution gathers the relevant evidence. A separate business Case could later group follow-up work such as contacting a supplier, verifying an amended document, and preparing an audit packet.

Neither the user's message nor the generated report substitutes for the underlying work identities.

## An unresolved tension

Durable work improves continuity but also introduces scheduling, lifecycle, cancellation, and data-retention obligations. Artemis treats those as core architectural concerns rather than hiding them in prompt text.

**Status:** current Artemis has durable-execution foundations; the full conversation-independent Workspace / Execution / Case model described here is part of the evolving vNext design. [Status](STATUS.md).
