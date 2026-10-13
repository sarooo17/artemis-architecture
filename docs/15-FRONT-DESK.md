# Front Desk: interaction is not execution

> **Design thesis:** a single conversational entry point should let people navigate and supervise work without requiring the conversational agent to become an all-powerful business worker.

## Why a Front Desk?

If a user asks "Is the report ready?", "Can you open the supplier table?", or "Start reviewing overdue invoices", these requests are different in kind.

Some concern the workspace itself. Some require the status of existing work. Others should start or steer a durable Execution. Treating all of them as an invitation for the chat model to directly operate every connected system blurs both responsibility and authority.

Artemis's vNext direction separates:

- **Front Desk:** interprets user intent, resolves references, answers interaction-level questions, and controls work through authorized operations.
- **Execution:** owns substantive autonomous work that may require business capabilities, compute, delegation, external waits and verification.
- **Work Surfaces:** show and support interaction with relevant business objects, artifacts and state.
- **Attention:** routes approvals, questions and meaningful updates from work back to the person.

## One entrance, many outcomes

The same input surface can support lightweight answers, opening a work surface, steering an existing task, initiating new work or responding to a pending approval. It need not create an autonomous agent run for every message.

The Front Desk also need not be a privileged business super-agent. In the target model, business actions have their own governed execution boundaries; the conversational control layer cannot silently inherit those powers.

## A practical illustration

A user asks: **"Why is this invoice still waiting?"**

The system should identify which invoice or work item the user means, inspect the appropriate status and evidence, and give a clear answer. If solving the issue requires cross-system investigation, it can begin a separately addressable Execution. If it requires an approval, the system can surface that decision rather than invent a workaround.

The user retains one continuous entry point while the underlying kind of work changes.

## An important trade-off

A conversational gateway that remains lightweight requires reliable binding between user intent and existing objects. Focus, selected surfaces and prior conversation can help, but ambiguity should be resolved rather than guessed.

**Status:** Artemis already has interaction and agent orchestration foundations. The unified Front Desk/control-plane division described here is a vNext architectural target. [Status](STATUS.md).
