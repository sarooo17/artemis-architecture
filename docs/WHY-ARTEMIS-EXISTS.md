# Why Artemis exists

> **A product thesis:** business work is not a chat transcript, a navigation menu, or a collection of isolated tool calls.

## The underlying problem

In a company, a seemingly simple request often crosses multiple systems, people and time horizons.

"Why has this order not shipped?" may require checking a sales order, stock, supplier commitments, a delivery record and an approval. Explaining the situation is useful, but actually resolving it may take longer than one AI response.

Today's products solve different parts of this problem: conversational assistants help interpret intent; business software holds records; workflow systems coordinate known steps; agent frameworks help build reasoning-driven automation. Each is valuable. The tension is the gap *between intent and verifiable business outcomes*.

Artemis explores an AI-native environment where the user describes the desired outcome and the system can assemble the appropriate context, work, capabilities and interface **without making the chat transcript the source of truth**.

## Five principles

### 1. Start from work, not software modules

People think in outcomes: resolve a discrepancy, investigate a delayed order, prepare a report. They should not have to translate every request into the navigation structure of multiple tools.

### 2. One place to interact, many independently addressable activities

The target is one Workspace with a persistent conversation and a collection of Work Surfaces, Executions and Artifacts. Moving between views changes what is relevant; it does not require a new conversational silo. Individual work can persist independently.

### 3. Let context follow purpose

A global history is not a license to inject every past message into every operation. The right context depends on what the person intends, what they are looking at, what the work needs and what information they are permitted to access.

### 4. Make autonomy accountable

An AI suggestion, authorization to act and verification that an action succeeded are different things. Durable work needs clear identities, boundaries and evidence, especially when real business records can change.

### 5. Treat time as part of the system

Business processes pause. Suppliers respond later. Reviews require people. Deadlines arrive. An assistant should be able to wait for meaningful future conditions without spending model compute pretending that time has not passed.

## Why this is an architectural problem

Simply adding memory, more tools, more agents or richer widgets does not solve the whole problem. The ownership of work, authority, context, continuation and presentation must be coherent.

Artemis is an attempt to bring these boundaries into one architecture. It is not a claim that the individual techniques are unique, nor a claim that every part of the target is fully deployed today.

## What Artemis does not seek to replace

Artemis is designed around existing business systems as authoritative sources. It is not a new ERP database or a universal substitute for workflow engines and integration platforms.

The objective is a more natural and governable **work environment above existing systems**.

## Explore

- [Architecture signatures](DESIGN-PRINCIPLES.md)
- [One Workspace, changing context](00-ONE-WORKSPACE.md)
- [Architectural trade-offs](ARCHITECTURAL-TRADEOFFS.md)
- [Interactive demo](https://demo.underlay.studio)

**Status:** this document explains Artemis's product thesis and vNext design. It does not constitute an availability or performance guarantee. See [architecture status](STATUS.md).
