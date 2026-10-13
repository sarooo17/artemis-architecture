# Architecture status and publication scope

**Editorial review:** 14 October 2026. This is a qualitative public architecture snapshot, **not** a live deployment certification or release checklist. Implementation notes are based on reviewed internal engineering contracts and code; the actual deployed configuration may differ.

## How to read this repository

Artemis has a current application/demo architecture and a separate, accepted **vNext target** under incremental development. A component existing in code is not the same as that component being wired into the current host, available in the demo, or qualified for production use.

| Area | Existing foundation / current boundary | vNext design direction or limitation |
| --- | --- | --- |
| **User experience** | Workspace, chat, multi-tab and generated read-oriented UI foundations | One global Conversation per Workspace, with independently persistent Work Surfaces and dynamically assembled context. **Not the current conversation model.** |
| **Execution** | Durable-execution, recovery, budget and verification primitives surround a predominantly model-centric runtime | Runtime-owned continuation, independently addressable concurrent Executions, and a unified work-first lifecycle |
| **Front Desk** | Existing conversational entry, routing and execution controls | A lightweight Workspace control plane rather than a business-system super-agent |
| **Capabilities** | Canonical semantic contracts, capability categories, domain packs, compact discovery/invocation patterns, and provider/host integration foundations | Fully task-scoped environment compilation, consistently governed discovery and wider provider interoperability |
| **ERP connections** | ERPNext-backed capability layer and typed **read-oriented** provider adapter; mappings retain ERP-specific assumptions | Additional ERP adapters and verified semantic parity. **Switching to arbitrary ERPs is not currently plug-and-play.** |
| **Business writes** | ERP-facing access is primarily read-oriented; some draft/prepare interfaces and non-executable contracts exist | Governed business actions and verifiable committed results. **Do not infer live ERP mutation support from a write contract or demo UI.** |
| **Event Intelligence** | Separately published EI implementation supports persistent temporal conditions and host-owned activation; Artemis has integration work | Exact Execution-centered resumption and dependency-based wake propagation in the unified vNext runtime. **Library features do not automatically equal deployed Artemis features.** |
| **Context, knowledge and memory** | Context/memory retrieval, scoping and evidence-governance foundations | Purpose-specific context projections, explicit Knowledge Sources, cross-source provenance and governed lifecycle across the new Workspace |
| **Intelligence and teams** | Existing adaptive-execution and agent-orchestration components | Differentiated deterministic/bounded/open reasoning, minimal-first team composition and governed recomposition |
| **Work Surfaces and direct actions** | Existing UI, artifacts and interaction/action contracts | Durable software surfaces, where a normal direct action does not need an autonomous Execution |
| **Cases and automation** | Durable work and event/automation building blocks | Long-lived Case semantics and precise separation between launching new work and resuming existing work |
| **Operational governance** | Existing policy, authority, execution budgets, traces and verification foundations | Task-scoped access escalation, hierarchical budgets, causal explainability and end-to-end qualification |

## Important status distinctions

- **Documented:** an architectural rule or interface has been described.
- **Implemented foundation:** relevant code or contract exists. It may be isolated, partially connected or limited in scope.
- **Integrated:** the component is connected to the relevant host or workflow. This still does not prove the complete end-to-end behavior.
- **Demonstrated:** a specific user-visible scenario has been reproduced.
- **Qualified:** the intended behavior has passed appropriate tests for the deployment context.

These terms are **not interchangeable**. Nothing here implies that every target capability is available in the public demo, that all integrations have identical capabilities, or that all enterprise reliability properties have been independently certified.

## What these notes intentionally do not disclose

- Private source architecture, implementation code, deployment layout, credentials or internal connection details.
- Sensitive security policies, complete threat models, failure-recovery mechanisms and operational thresholds.
- Proprietary routing, ranking, model/compute selection or prompt/context internals.
- Private schemas and provider mappings, unpublished benchmarks, customer data or development backlog details.

The objective is **technical transparency about architectural decisions and trade-offs**, not an implementation manual or a security assurance report.

## Interpretation

If a document says "Artemis explores," "the design aims," or "vNext," it describes an architectural direction. When a foundation is mentioned, it must not be interpreted as a statement that every related product flow is shipped. The [guided demo](GUIDED-DEMO.md) explains this distinction from a visitor's perspective.

This distinction should be preserved in future updates.
