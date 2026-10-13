# Capability taxonomy, modular packs and provider adapters

> **Design thesis:** Artemis should describe *what can be done* independently of *which system performs it*, while keeping discovery compact, permissions explicit, and provider limitations visible.

The Capability Fabric is not simply a growing list of model-visible tool definitions. It is designed as a semantic layer that organizes operations from different business systems and Artemis's own internal functionality.

## A capability has more than one dimension

Different questions about an operation should not be mixed together.

| Dimension | Illustrative categories | Question answered |
| --- | --- | --- |
| **Business / functional domain** | Customers, sales, procurement, finance, inventory; workspace, files, memory, artifacts | What area does this operation belong to? |
| **Operation kind** | Search, read, analyze, prepare, execute/write, verify, metadata | What kind of work is being requested? |
| **Risk and effects** | Low/medium/high risk; informational vs. consequential change | What could happen if the operation is invoked? |
| **Exposure** | Agent-accessible, host-internal, UI-accessible, or integration-facing | Through which surface, if any, should this capability appear? |
| **Backing system** | Internal host function, external provider, ERP adapter, other integration | Who actually carries out the operation? |
| **Lifecycle and availability** | Implemented, experimental, unavailable in a particular context | Can this operation be used for this task right now? |

These dimensions are intentionally independent. An operation can belong to finance, be a read, carry a particular risk classification, and be available only to a permitted assignment. Its business category does not automatically grant permission to invoke it.

The categories above are a **public conceptual summary**, not a complete enumeration of private capability contracts or live permissions.

## Modular capability packs

Capabilities are organized into domain-oriented collections rather than being exposed as a flat, all-access list.

The architecture distinguishes, for example:

- **Business capabilities** for operations over records in a connected ERP or other system.
- **Workspace and experience capabilities** for working with surfaces and user-facing state.
- **Document and artifact capabilities** for information and outputs.
- **Memory and knowledge access** where authorized and appropriate.
- **Specialized integration capabilities** for the operations a connected provider actually supports.

In the ERP layer, **curated** operations provide intentional business-facing behavior, while **metadata-informed/generated** operations can broaden eligible read coverage in a controlled way. Generated does not mean automatically authorized, enabled, or safe for writes.

The aim is to keep the semantic catalog expressive without forcing every operation into the model's initial context. A small discovery/invocation surface exposes task-relevant, permitted capabilities as needed.

## Semantic operation versus concrete adapter

Consider a generic business intent:

**"Find outstanding purchase orders for this supplier."**

At the semantic level, the task asks for an operation over purchasing information. The capability layer can express that meaning without requiring the agent to reason directly about a particular vendor's API names.

Conceptually:

```text
Business intent
     |
Semantic capability
     |
Governed capability selection
     |
Provider-specific adapter
     |
Authoritative business system
     |
Normalized result + source provenance
```

*Illustrative logical boundaries, not an implementation topology or public API.*

An adapter translates between a system's particular representation and the semantic operations Artemis understands. The source system remains authoritative; the adapter does not magically make different ERPs identical.

This separation also matters beyond ERP: a runtime should be able to evolve an integration implementation without requiring a different user-facing concept for every provider.

## Does this mean ERPNext can be swapped for another ERP?

**That is an architectural objective, not a currently guaranteed one-click capability.**

Artemis has an ERP provider abstraction and a typed read-oriented adapter foundation, with ERPNext as the present concrete ERP-backed environment. The existing canonical ERP mappings still contain ERPNext-specific assumptions. Adding another ERP would require a real provider adapter and validation that equivalent business operations can be represented correctly.

A credible adapter needs to reconcile, where relevant:

- Meaning and relationships of business entities.
- Field and identifier mappings.
- Search/filter semantics and result normalization.
- Authentication, tenant scope and permissions.
- Differences in operational workflows and write behavior.
- Error states, side effects and post-action verification.
- Capabilities that simply have **no equivalent** in the target ERP.

For example, a capability to search customers may be reasonably portable, while a vendor-specific approval transition might have no exact equivalent. Artemis should report such gaps rather than pretend to support a universal operation.

**Changing an adapter should not require rewriting the entire reasoning architecture, but it may require new mappings, capability implementations and conformance tests.**

## Discovery, federation and governance

A single semantic catalog can conceptually combine capabilities implemented inside Artemis with capabilities supplied by other systems, without treating all of them as equally exposed or callable.

The model-facing surface stays compact. Discovery returns what is relevant and permitted; execution still passes the appropriate policy and authority boundaries.

An available connection does not imply an all-access agent. A capability found in metadata is not necessarily executable. Read support does not imply write support.

This is why **provider flexibility, capability discoverability and authorization are separate concerns**.

## The value and the cost of abstraction

The architectural advantage is flexibility: business intents and worker environments can evolve independently of particular backend implementations, and new integrations have a common conceptual place in the runtime.

The cost is substantial. Vendor semantics vary, even for familiar terms such as "customer", "invoice" or "approved". Over-normalizing those differences can be worse than admitting that a capability is unavailable.

Artemis therefore treats a shared semantic layer as a useful boundary to **earn through implementations and verification**, not as proof that all systems are already interchangeable.

## What remains private

These notes do not disclose implementation-specific mapping tables, provider routing internals, private schemas, credentials, policy rules, connection topology or current integration limitations beyond the high-level maturity boundary.

**Status:** canonical capability contracts, modular ERP capability collections and a typed ERP provider adapter exist as foundations. Fully interchangeable multi-ERP support is **not established** by those foundations alone. See [Architecture status](STATUS.md) and [Capability Fabric](02-CAPABILITY-FABRIC.md).
