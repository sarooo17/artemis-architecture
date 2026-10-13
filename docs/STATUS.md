# Architecture status and publication scope

**Snapshot:** 13 October 2026. This is a public conceptual snapshot, not a release checklist.

Artemis has a running product/demo architecture and a separate, accepted **vNext design**. The new semantic model is being implemented incrementally. These notes describe the overall direction without implying that every described subsystem has completed its integration or production qualification.

| Area | What can be said publicly |
| --- | --- |
| Unified Workspace / global conversation | The current workspace includes chat and surface foundations, but the one-global-conversation architecture independent from tabs and Executions is a vNext goal, not an assertion about the present product. |
| Artemis product/demo | Active implementation and demonstrations exist; this repository does not document supported product operations or production guarantees. |
| Capabilities | Semantic capability abstraction, compact discovery/execution surface, and task-relevant access have implemented foundations. |
| Execution and verification | Durable execution, budgets, recovery and verification have existing building blocks; their unified vNext semantics are still being developed. |
| Event Intelligence | A separate public EI project is implemented and published; Artemis integration and precise vNext wake/resume behavior should not be assumed to be fully deployed. |
| Context and memory | Existing memory/context primitives; fuller environment projection and governed cross-source reasoning are vNext design work. |
| Dynamic team composition | Current agent orchestration exists; minimal-first composition and governed recomposition are target architecture. |
| Cases, knowledge and learning | Explicit Case / KnowledgeSource / learning-promotion semantics described in the notes are target architectural concepts, not assumed production features. |
| Adaptive cognition and teams | Current adaptive primitives exist; the complete runtime-owned continuation/team model is a target. |
| UI / work surfaces | Existing workspace and generated-UI work; globally organized conversation and independently managed surfaces belong to the target direction. |
| Case / long-lived practice | Target architectural concept, not a statement of product availability. |

## What these notes intentionally do not disclose

- Internal repository architecture, implementation source, deployment or service topology.
- Sensitive security implementation, access policies, credentials, threat-model specifics, or production limits.
- Private schemas, algorithms, tuning thresholds, prompt packages, routing policies, and performance or cost figures.
- Internal roadmaps, unreleased integration steps, proprietary evaluations, and customer data.

The objective is **technical transparency about decisions and trade-offs**, not an implementation manual or a security assurance report.

## Interpretation

If a public note uses phrases such as "Artemis explores," "the design aims," or "vNext," it is explaining an architectural direction. If it describes an existing foundation, it is not asserting that the complete end-to-end behavior is available to all users.

This distinction is intentional and should be preserved in future updates.
