# Many activities, one place to stay in control

> **Design thesis:** several tasks should be able to proceed independently without monopolizing the user's conversation or hiding requests for human attention in individual tabs.

## The experience problem

A person may be reviewing an invoice, waiting on a contract approval and generating a report at the same time. In a chat-by-chat model, progress and questions often become scattered across threads.

Artemis's target treats **multiple Executions** as first-class occupants of one Workspace. They have independent identities and states, while the conversational input remains available.

```text
WORKSPACE
  Conversation: always available
  Work surfaces: invoices, contracts, reports
  Executions:
    invoice review  — running
    contract check  — waiting for approval
    sales summary   — completed
  Attention:
    one decision requested
```

*Illustrative, not a screenshot or deployed system schema.*

## Work status is different from a chat transcript

The architecture points toward a compact, global view of ongoing work. It can show meaningful phases, waits, failures and results without forcing a user to open the exact tab or chat where an activity began.

It should avoid fabricated completion percentages: "Waiting for supplier approval" is more informative than "87%" when progress cannot genuinely be measured.

A user should be able to inspect, steer or cancel permitted work without interrupting unrelated tasks.

## Human attention is its own concept

An approval, a missing piece of information, a completed result and a notification are not the same thing.

Artemis distinguishes **what decision is needed** from **how it is delivered or presented**. This matters when multiple activities request input around the same time.

A background task needing permission should not gain that permission by simply displaying a notification. Likewise, reading a message does not count as approval.

## Parallel work is not unlimited work

Concurrency must respect resource budgets, business conflicts, user permissions and system capacity. More simultaneous tasks are not necessarily more useful.

**Status:** current Artemis has work status and approval foundations. A global, multi-Execution attention experience independent of chat/tab boundaries is a vNext direction. [Status](STATUS.md).
