# Reliability and autonomy belong together

> **Design thesis:** an agent should not be considered autonomous merely because it can keep asking a model what to do next.

Useful autonomy needs resource limits, recovery semantics, explicit dependencies and predictable control when systems are slow or unavailable.

## Not every step deserves a model call

An ordinary computation, a known safe retry, a structural validation and an external wait have different requirements from open-ended analysis. Treating them all as model-inference turns adds cost and uncertainty.

Artemis's direction is to distinguish those operation types and reserve deeper cognition for uncertainty that actually requires it.

## Resource budgets have scope

A design for multiple simultaneous activities needs more than a global limit on model tokens. Budgets can apply across a workspace, an Execution and its delegated subwork, and the individual operations using models, tools or compute.

The vNext direction is **hierarchical and multidimensional resource governance**: starting parallel tasks should not accidentally multiply unlimited spending, and retries or event storms should not bypass limits. Hard safety and resource boundaries are not negotiated by a model; within permitted choices, the system can still favor more or less expensive cognition as appropriate.

An active task and a task that is merely waiting are not equivalent consumers of compute. Any budget policy must keep that distinction.

## Progress without busy waiting

A long-lived Execution may be idle while waiting for a person or a future event. Waiting should preserve durable intent and dependencies rather than occupying a running agent loop.

When a condition is met, the resumed task must still check current state and authority.

## Recovery is a work concern

Partial results, cancelled tasks, changed records, competing writes and stale observations are normal in business systems. A durable task needs to represent these states honestly and avoid silently repeating consequential effects.

The target treats resource governance, fairness, verification and recovery as runtime responsibilities. The specific scheduling, infrastructure and retry machinery remain private.

## Control should stay responsive

People need to inspect, approve, steer or stop work even when other tasks are busy. Maintaining that separation is part of the architectural goal, not just a UI detail.

**Status:** existing resource, budget, retry and execution primitives inform this work; the complete vNext reliability model remains subject to implementation and qualification. See [Status](STATUS.md).
