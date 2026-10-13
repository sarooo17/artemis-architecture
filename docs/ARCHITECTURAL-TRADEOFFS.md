# Architectural trade-offs

> **The goal is not maximal automation. It is the smallest understandable system that can accomplish the work safely.**

Every architectural direction involves costs. This note explains the choices Artemis is exploring and the problems they introduce. It is a comparison of **design approaches**, not a scorecard claiming superiority over individual vendors.

| Question | Why Artemis favors this direction | The trade-off |
| --- | --- | --- |
| Chat as work container or Workspace with independent Executions? | Work can survive the turn, remain addressable and span multiple surfaces | Durable state, lifecycle and correlation add complexity |
| Full transcript or dynamic context per operation? | Only relevant, permitted and fresh information should reach the current operation | Retrieval and reference resolution can miss important details |
| Large static tool catalog or compact capability discovery? | Smaller model-facing surface, independent semantic operations and contextual access | Discovery requires reliable relevance and authorization handling |
| Model loop for every step or differentiated continuation? | Use deterministic compute, bounded decisions and open reasoning for different needs | More operation types and runtime coordination to maintain |
| Frequent polling or event-based wake/resume? | Wait for meaningful changes without continuous inference | Event consistency, correlation, cancellation and stale wake handling |
| Universal worker or task-specific environments? | Resources and access better match the assignment | Environment expansion must be both usable and governed |
| One fixed agent team or minimal-first adaptive composition? | Avoid unnecessary specialists and independent tasks | Team changes can introduce coordination overhead |
| Answer-centric success or evidence-based completion? | Distinguish a plausible response from an actually verified outcome | Verification adds cost, latency and sometimes uncertainty |
| Static modules or intent-shaped Work Surfaces? | Users interact with the work and its outputs rather than only navigating systems | Generated experiences still need stable interaction contracts and accessibility |
| Replace the ERP or operate above existing systems? | Keep established sources of truth and investments intact | Integration semantics, freshness and provider limitations remain real |

## What a comparison with existing platforms would require

A public, meaningful comparison should compare similar layers and specific scenarios. An enterprise assistant, an agent framework, a workflow engine and an ERP copilot are not interchangeable product categories.

Any future named comparison would need:

1. Precisely identified vendor product and version or dated documentation.
2. A common task and constraints.
3. A distinction between advertised support and directly reproduced behavior.
4. Measurable evidence for completion, resumption, policy enforcement, cost and usability.
5. Explicit unknowns and limitations.

Until those tests exist, this repository does not publish competitive rankings or feature checkmark tables. Detailed vendor intelligence is not part of these public materials.

## The key claim

Artemis's differentiation is an **integrated design thesis**: continuous workspaces, durable executions, dynamic context, compact capabilities, temporal intelligence, governed actions and verifiable results **support the same unit of work**.

Individual techniques are not exclusive to Artemis. The hard engineering work is making their boundaries and user experience coherent.

**Status:** some foundations exist today, while important parts of the integrated target are in development. See [architecture status](STATUS.md).
