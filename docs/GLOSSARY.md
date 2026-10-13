# Glossary: the boundaries behind Artemis

Artemis uses a number of related terms that are easy to confuse. These are **public conceptual definitions**, not executable contracts or guaranteed product features.

| Term | What it means | What it is *not* |
| --- | --- | --- |
| **Workspace** | The user's coherent environment for conversation, work, surfaces and artifacts | A single running agent or a collection of disconnected chat sessions |
| **Global Conversation** | The proposed continuous communication channel within one authorized Workspace | The only store of task state or the entire model context |
| **Work Surface** | A persistent, interactive representation of work or a resource | Merely a chat message, a browser tab identity or a long-running Execution |
| **Focus** | What is currently visible or selected and might help interpret intent | An unconditional instruction, the requested target or an authorization grant |
| **Context Projection** | Relevant information assembled for a particular operation | The entire conversation transcript or an unbounded memory dump |
| **Execution** | A durable, independently addressable unit of work with progress, evidence and an outcome | A chat session, a tab or every direct UI interaction |
| **Case** | A business concern that may connect several Executions and artifacts over time | A permanently running agent, a conversation or a parent task by default |
| **Attention** | A surfaced request for user input, an approval or an important update | The underlying approval decision itself, or proof it has been granted |
| **Artifact** | A durable work output such as a report or document | A temporary UI rendering or verified business state by definition |
| **Capability** | A semantic operation supported by a particular system under constraints | A permission, an entire professional workflow or necessarily a public MCP tool |
| **Provider Adapter** | An integration boundary translating between semantic operations and a concrete provider | A guarantee of feature parity across every vendor |
| **Skill** | A reusable, task-specific method, potentially composed of several governed resources | A business domain, a raw API operation or necessarily a Markdown prompt |
| **Specialist** | A reusable expertise profile | The automatically authorized operator of everything in that domain |
| **Agent Blueprint** | A reusable configuration for a possible worker | A perpetually running agent or an authority grant |
| **Worker Profile** | The effective, assignment-scoped environment used for one piece of work | A blanket, all-tools role inherited unchanged across every task |
| **Knowledge Source** | An inspectable corpus intentionally available as reference material | Automatically learned memory or authoritative live ERP state |
| **Memory** | Scoped and governed reusable knowledge | Conversation history, compaction, current operational state or an external policy override |
| **Automation** | A definition of future circumstances under which new work may launch | A worker's identity or an already-running Execution |
| **Event Intelligence** | A temporal event-condition layer that can produce facts and host-owned activations | A chat scheduler with unlimited permission or the owner of business task state |
| **Continuation** | The next operation or state transition owned by a durable work engine | Simply prompting the same model again |
| **Authority** | The permitted scope of an action for a principal in the current context | Model confidence, a connected credential alone or instructions from a document |
| **Evidence / Verification** | Source material and checks supporting a claim or a task outcome | A persuasive model explanation or a successful-looking tool response |

## A small example

Someone asks to investigate a supplier discrepancy. The **Front Desk** interprets the intent; an **Execution** may investigate using permitted **capabilities**. A purchasing **Skill** can supply a method, a company **Knowledge Source** may supply policy, and current ERP records provide world evidence. If a corrected document is expected next week, **Event Intelligence** may track the relevant future condition. The **Case** can keep the business matter coherent across several work items.

A **Work Surface** presents the invoice and outcome. A normal user edit on that surface does not automatically become a new Execution. **Authority** governs actions, while **verification** determines whether the requested real-world result was achieved.

Some of these semantics are part of Artemis's **vNext design**, not all live demo behavior. See [Architecture status](STATUS.md) and [The architectural signatures](DESIGN-PRINCIPLES.md).
