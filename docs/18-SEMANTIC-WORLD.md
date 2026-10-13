# Business intent over heterogeneous systems

> **Design thesis:** users should express business goals without having to know which underlying system, endpoint or model-facing tool name can fulfill them.

## Beyond a tool collection

A business workflow may span ERP records, documents, approvals, collaboration tools and external providers. These systems have different data structures and operation names.

Artemis explores a shared **semantic layer of capabilities and work artifacts**. An agent reasons about an operation's meaning while the supporting provider or protocol remains an implementation concern.

This does not mean pretending all applications are identical. The provider's actual state, permissions, capabilities and limitations still govern what can be done.

## A protocol is an integration boundary, not the product's mental model

MCP and other interfaces can connect useful systems. But a business-facing operation should not need to be defined by one transport or SDK.

In the Artemis design, **semantic contracts** help components exchange the meaning of work, evidence and authorization while keeping model-specific and provider-specific machinery replaceable.

The ambition is an AI-native layer *over* existing business systems, not to replace ERP databases or silently create a second system of record.

## An illustrative request

**"Find orders that are blocked because the supplier delivery is late, and show me which customers may be affected."**

This intent crosses procurement and sales concepts. The system must identify suitable available data, retrieve records within permitted scope, correlate the evidence and present an intelligible result. If action is requested, it passes through a separate governed boundary.

The user should not need to select a series of ERP modules by hand, and the assistant should not assume that a plausible textual answer is authoritative business truth.

## A key limitation

Semantic portability is not a claim that every ERP or SaaS system is already supported or that provider differences can be erased. Capability availability and result quality depend on actual connections, schemas and authorization.

**Status:** Artemis has business-capability and shared-semantic-contract foundations. The broader provider-independent composition and work model continues to evolve. [Status](STATUS.md).
