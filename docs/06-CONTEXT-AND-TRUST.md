# Context is an environment, not a transcript dump

> **Design thesis:** relevant information should be assembled for the work at hand, and every piece should retain its provenance and permitted use.

## An agent can read conflicting worlds

A business task may involve current ERP records, internal notes, previously learned preferences, a newly uploaded document, and external research.

The system should be able to reason across them without pretending they are equally authoritative.

For example, a supplier email may be useful evidence that banking details changed. It is not, by itself, authorization to update bank details in the ERP.

## The same conversation can produce different contexts

In the vNext direction there is no need to open a different chat every time the person switches business topics. The **global Workspace conversation** persists, while each operation receives a context projection based on intent, focus, references, evidence freshness and the purpose of that operation.

The historical transcript is a retrievable source; it is **not** automatically the full context of the next model call. See [One Workspace, changing context](00-ONE-WORKSPACE.md).

## Context is task-shaped

Artemis develops the idea of a task-specific **environment**: relevant information, accessible capabilities, allowed actions, computational resources, and resource limits, presented together for a particular operation.

This avoids the assumption that everything an agent might need must be inserted into a giant prompt beforehand. Additional context or memory can be requested when it is actually necessary.

## Four useful distinctions

- **History** is what happened in interactions.
- **Execution state** is where durable work stands.
- **Memory** is reusable information retained across tasks.
- **Knowledge and evidence** are material with sources, freshness, and verification characteristics.

None should be silently substituted for another.

## Provenance survives summarization

A model-generated summary of an unverified document is not itself verified evidence. A current business record may outweigh an old remembered value for operational questions. A user preference has a different scope of authority from a company approval rule.

The aim is to keep these relationships visible, even when a worker combines data from different sources in one reasoning step.

## Memory should not silently become policy

The architecture also separates proposing something worth remembering from committing it as durable memory. This matters when information may be incorrect, externally supplied, stale, or tenant-specific.

**Status:** Artemis has context, memory, and evidence-governance foundations. The comprehensive task-scoped environment and cross-source trust model are part of vNext. [Status](STATUS.md).
