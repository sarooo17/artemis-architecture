# Teams formed for the work, not for a flowchart

> **Design thesis:** multi-agent execution should be proportional to the independence and expertise demanded by the task.

An arbitrary prompt should not automatically summon a coordinator, five specialists and a critic. Nor should one universal agent inherit every skill and system in the company.

Artemis's vNext direction is **minimal-first team composition**: start with the smallest adequate arrangement and introduce specialization, independent work or coordination where they are justified.

## Expertise is not hierarchy

A task may benefit from a single generalist, a domain specialist, a specialist using controlled compute, multiple independent specialists, or a genuinely coordinated team. This choice depends on the shape of the work and its dependencies rather than a fixed org chart.

A worker's name or role alone does not grant tools, credentials or company authority. Its effective environment remains scoped to the assignment.

## Differentiate help from independent work

A short opinion from a specialist may be an ordinary reasoning contribution. It does not require spawning an independently scheduled subagent.

A child Execution becomes useful when the subgoal has meaningful separate lifecycle: its own evidence, progress, dependencies, wait conditions, recovery, artifacts or completion requirements.

This distinction keeps delegated work understandable and prevents artificial agent proliferation.

## Teams can change

Suppose a finance review unexpectedly reveals an inventory valuation problem. The system may need a different expertise mix. The intended design supports governed recomposition rather than restarting everything or preloading all possible specialists from the start.

This introduces a real trade-off: dynamic composition can improve fit, but it complicates responsibility, costs and recovery. The objective is not maximal agent count; it is sufficient competence with visible ownership.

**Status:** current Artemis has agent/team and adaptive-execution foundations. The complete minimal-first composition and recomposition model is a vNext target. See [Status](STATUS.md).
