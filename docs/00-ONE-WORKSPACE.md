# One workspace, changing context

> **Design thesis:** one persistent workspace and conversation can support many contexts of work without fragmenting the user's history into separate chats.

This is a defining Artemis vNext idea. It is not simply a chat sidebar with different tab titles.

## The distinction

A typical chat-oriented environment starts with a conversation and attaches documents, tools and tasks to that conversation. Moving to another chat creates another implicit context boundary.

Artemis's target starts with a **Workspace**, then separates its durable parts:

- **One global conversation** as an ongoing communication channel within that workspace.
- **Work Surfaces** as persistent views of documents, business entities, tables, artifacts, dashboards or other material.
- **Executions** as independently addressable work that may run, wait, require input or finish.
- **Context** as a *computed projection* for the current question or operation, not the entire conversation history.
- **Memory, knowledge and evidence** as distinct sources that can inform the work when appropriate.

These objects relate to one another but are **not interchangeable**. A tab is not a chat. A tab is not a task. A task can exist without an open tab. One task can produce several surfaces; one surface can be useful across several tasks.

```text
WORKSPACE
  conversation  ── ongoing communication and steering
  surfaces      ── visible, interactive representations of work
  executions    ── durable tasks and their progress
  cases         ── optional long-running business concerns
  memory        ── scoped reusable information
  artifacts     ── durable outputs and evidence
  attention     ── things requiring a person's decision
```

*Conceptual model, not a deployed service diagram.*

## Changing focus is not changing conversation

Suppose a user opens a customer record, then an overdue invoice, then a quarterly report.

In a chat-centric product, the user may have to choose which conversation contains the right context. In the Artemis target, the global conversational entry point stays the same while the user changes the **active surface**.

A surface can contribute useful signals: the selected record, an open document, a highlighted table range, a visible artifact, or the current unsaved draft. These are **focus hints**, not permissions and not absolute commands.

If the user says, "Why is this amount different?", the selected invoice may help resolve "this." If the user instead says, "Show the open orders for Acme," the explicit request should take precedence even if an unrelated invoice remains visible.

The system must distinguish:
1. **Source focus:** what the person is looking at.
2. **Target:** what the request actually refers to.
3. **Disposition:** whether to answer, operate on a surface, launch work, steer existing work, or request clarification.

## Dynamic context is built per operation

A continuous conversational history does **not** imply sending its entire transcript to every model call.

A question about an invoice may need the current invoice, supplier history, the relevant prior decision and the authorized business capabilities. A question about a design document may need the focused document and a style preference—but not unrelated invoice details.

Conceptually:

```text
Current intent + explicit references + active focus
    + purpose of the next operation + authorized scope
                         ↓
            Relevant source selection
                         ↓
             Context for this operation
```

Each operation can have a different context projection, even when both operations occur in the **same conversation**. Context is retrieved and assembled for a purpose; it is not a fixed chat memory bucket.

This architecture also addresses context growth: a long history is retained and navigated separately from what a model actually needs at a particular moment.

## A workday without chat fragmentation

- At 09:00, the user reviews purchase invoices in one surface and asks for anomalies.
- At 09:05, a reconciliation Execution begins, with its own identity and evidence.
- At 09:10, the user switches to a sales dashboard and asks about one customer. The same conversational entry point remains available, while the active context changes.
- At 11:00, the reconciliation is waiting on a supplier event. It does not occupy or own the conversation.
- Later, the user returns to the earlier Execution or its artifact without searching for a special chat where it originated.

The system should preserve continuity **without mixing unrelated contexts**.

## The difficult parts

The design must handle ambiguous references, simultaneous work, evolving permissions, long histories, background updates and stale surface state. It cannot infer authorization from the current tab or leak one work item's context into another.

An important limit: "one conversation" is a product direction **inside the appropriate workspace and authorization boundary**, not a promise that every tenant, user and security domain shares a single transcript.

**Status:** an intentional vNext target, built on current workspace, focus, execution and context foundations. The full conversation-independent model is not being presented as already deployed. See [Status](STATUS.md).
