# An interface shaped by work

> **Design thesis:** the interface should help people understand and control work, not force intent into a fixed navigation tree.

## A user should not have to become an ERP operator

Many business applications are organized around entities and modules. Real requests often cut across those divisions:

"Show me which orders are blocked and help resolve the exceptions."

That request is neither a single page nor a single database table. Artemis explores an experience in which an intent can lead to the right information, a targeted interface, and an appropriate action boundary.

## One Workspace, one conversation, many surfaces

A central vNext principle is **one global conversation per Workspace**. Opening a new table, dashboard, entity or document changes the active work focus—it does not create another conversational silo.

The active surface may contribute relevant context, while an explicit user request can refer to something else. The system should resolve which work or entity is being addressed instead of tying every question to the visible tab.

[Read the full Workspace and dynamic-context note](00-ONE-WORKSPACE.md).

## Conversation is one surface, not the whole product

The direction combines:

- A conversational channel for intent, questions, and steering.
- **Work surfaces** that present relevant data, artifacts, and controls.
- An explicit view of running, waiting, completed, and blocked work.
- **Attention** for questions, decisions, and approvals that require a person.
- Durable artifacts that survive beyond the message in which they were produced.

An interface element should not secretly become a new long-running agent task merely because it was clicked. Direct UI actions and autonomous work need different semantics.

## Work Surfaces should behave like ordinary software

In the vNext target, a Work Surface is a durable, interactive view of a business resource or artifact—not merely an LLM response rendered as a card. Opening a table, selecting a row, sorting, filling out a form and editing a draft do not inherently require an autonomous agent.

The design distinguishes **local presentation**, **persistent surface state changes**, **bounded direct domain actions**, and **autonomous, multi-step Executions**. A permitted direct action can remain a normal software action even when it changes business state, with the appropriate authorization and verification. Conversely, a complex request that needs planning, retries or waiting may become a separate Execution.

Both user-initiated and agent-initiated interactions should follow the corresponding action boundary. UI state and uncommitted drafts must not be confused with confirmed changes in the system of record.

This is why Artemis's intended experience is **software interaction with optional autonomy**, not an agent invocation for every click.

## Generated UI is not unrestricted UI

The generated experience still needs predictable interaction contracts, accessibility, clear ownership of data and state, and governed actions. A compelling dashboard is not proof that the underlying business record was changed.

The ambition is not "a new screen for every prompt." It is a coherent way to move between intent, visible work, and outcomes.

## Why this matters

Separating conversation, work, and presentation makes it possible to continue speaking to the system while other tasks run or wait. It also makes success and failure visible without forcing users to inspect raw traces.

**Status:** Artemis has generative-UI and workspace prototypes; the global conversation and independently composed work-surface model is a vNext target. [Status](STATUS.md).
