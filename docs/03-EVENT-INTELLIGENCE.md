# Event Intelligence: the future as a first-class input

> **Design thesis:** waiting for a future condition should not require keeping an LLM loop active.

## An event is not yet a reason to act

"An invoice was created" is an event. "The invoice was created, exceeds a threshold, and the matching approval has not arrived within the expected window" is a meaningful condition.

Artemis explores **Event Intelligence (EI)** to turn incoming signals into durable conditions that can be evaluated across time and, when appropriate, resume work.

EI is not merely a notification feed, and the objective is not to ask a model to repeatedly poll an API.

## The separation of responsibilities

Conceptually:

1. **The agent or user specifies a future condition.**
2. **EI maintains and evaluates that condition** as relevant signals arrive.
3. **The condition becomes satisfied**, with associated evidence.
4. **The host decides what continuation is appropriate.**
5. **Artemis resumes the corresponding work**, subject to current permissions and state.

An external event is data, not a command. Even a valid event match does not grant permission to perform an action.

## Deterministic temporal evaluation, with bounded semantics when needed

The separately published EI project is **deterministic-first**: it can evaluate structural and temporal patterns without continuously calling a model. A bounded semantic evaluator can be used selectively when a condition cannot be represented adequately by structural data. This is different from turning all incoming events into a prompt.

The public EI implementation also supports the distinction between **conditions as durable facts** and **activations that wake a particular host-owned continuation**. Not every meaningful condition needs to launch an agent. Some conditions can be composed into higher-level, derived events without waking a task at all.

EI is **embedded and host-owned**: the host retains responsibility for connected event sources, authorization, continuation identity and delivery. The host can use a durable target other than a conversation; Artemis's exact Execution-centered wake contract is a vNext direction.

## Beyond simple triggers

The interesting problems are temporal and relational: ordered events, absence, repeated events, bounded windows, correlations between sources, or higher-level conditions inferred from simpler facts.

In this design, a condition can stand independently of the conversational turn that originally defined it. Work can be dormant until something meaningful changes.

### A hypothetical example

"When the supplier responds **and** the revised invoice is available, revisit the discrepancy. If the response does not arrive before the deadline, request human attention instead."

This involves multiple future facts, a deadline, and a continuation that can have a different outcome depending on evidence.

## Why EI and Execution must remain separate

Event Intelligence evaluates *when a condition is met*. Artemis owns *what business work the condition should resume*. The event layer should not silently create authority, overwrite task state, or force every waiting task into a new conversation.

A key vNext direction is to resume the **exact waiting Execution**, not to indiscriminately wake its entire parent/child tree. A parent should resume only when its declared dependency or join condition is met. **Launching new work from an automation** and **resuming already-waiting work** are separate semantics.

## Independent public project

The underlying exploration also exists as **[MCP Event Intelligence](https://github.com/sarooo17/event-intelligence)**, a separate public package with its own documentation and licensing. That project and this Artemis architecture publication have different licensing scopes.

**Status:** EI has an independently published implementation. Its integration with Artemis and the precise Execution-centered wake semantics are evolving; do not read this note as a claim of full production deployment. [Status](STATUS.md).
