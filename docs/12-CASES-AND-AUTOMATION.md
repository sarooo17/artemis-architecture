# Work that outlives a task

> **Design thesis:** a business matter can persist for weeks without being one endlessly running agent execution.

A supplier onboarding, contract renewal, dispute or complex order exception may consist of many activities separated by human decisions and external events.

The Artemis target distinguishes three time-related concepts.

## Execution: a unit of work

An Execution owns a particular goal, progress and outcome. It may perform steps, delegate independent work, wait for a condition, or terminate with a verified or unresolved result.

## Case: continuity across work

A **Case** is an optional longer-lived business concern. It can collect related Executions, artifacts, relevant business entities and outstanding questions, even when nothing is actively running.

A Case is **not** a permanently thinking agent, a parent Execution, or a chat thread.

For instance, a disputed invoice may have one Execution for reconciliation, a later one for reviewing a corrected document, and another for the final business action. The Case is the continuity across them.

## Automation: start future work

An automation can launch new work under configured conditions. An Execution that is already waiting should instead be **resumed**, not replaced by a new task with a similar title.

Event Intelligence helps with meaningful future conditions, but it does not own business authorization or completion.

These distinctions make a long-running concern inspectable without requiring idle model compute between real events.

**Status:** event/automation and durable-execution foundations exist. The formal Case model and full target separation of launch-versus-resume remain vNext design work. See [Status](STATUS.md).
