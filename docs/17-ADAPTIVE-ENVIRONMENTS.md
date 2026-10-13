# An environment fitted to the assignment

> **Design thesis:** the right agent is not one that always has every tool, every document and every resource. It is one whose effective environment can be composed—and safely adjusted—for the work.

## The environment is more than a prompt

An operation may depend on current business data, relevant company procedures, reusable memory, computational resources, allowed capabilities and budget. These are distinct resources with different access and freshness rules.

Artemis explores an **assignment-specific environment** rather than granting a worker a broad, permanent set of tools and context because of its nominal role.

A finance specialist reviewing supplier invoices might receive relevant invoice and purchase-order access. It would not automatically receive unrelated employee records, administrative credentials or every connected SaaS application.

## Start with enough, expand only when necessary

If the task later needs a missing resource, the system should identify the type of gap instead of reflexively using a more expensive reasoning model.

Examples:

| What is missing? | Appropriate direction |
| --- | --- |
| A relevant fact | Retrieve permitted context or current evidence |
| A business operation | Discover whether an authorized capability exists |
| A mathematical transformation | Use controlled compute where appropriate |
| Particular expertise | Add a relevant specialist or recompose the team |
| A future external result | Register a meaningful wait |
| Authorization or a decision | Request the appropriate human/policy action |
| Genuine problem-solving capacity | Consider deeper reasoning |

This is conceptual behavior, not a public decision algorithm or a list of internal signals.

## Dynamic does not mean ungoverned

A worker must not grant itself permission by claiming a task is urgent, by quoting a website or by remembering a previous user's approval. A change in effective environment can introduce new relevant resources only through the appropriate boundaries.

The goal is to combine adaptability with a smaller initial cognitive and tool surface.

## Why it matters

This design can reduce irrelevant context and helps make model/tool use match the task. It also improves clarity when an operation is blocked: missing capability, stale information and insufficient cognition are different problems with different remedies.

**Status:** current Artemis includes context/capability and adaptive-execution foundations. Complete per-assignment environment composition and governed expansion are vNext targets. [Status](STATUS.md).
