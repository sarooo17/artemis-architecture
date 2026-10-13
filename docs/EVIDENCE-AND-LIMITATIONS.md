# Evidence, maturity and limitations

> **An architectural aspiration is not a verified product capability.**

This repository deliberately mixes discussion of implemented foundations with longer-term architectural design. The distinction must remain visible to anyone evaluating Artemis.

## Reading the status of a claim

| Label | Meaning | Minimum acceptable public evidence |
| --- | --- | --- |
| **Implemented foundation** | A relevant component or subsystem exists | A bounded and accurate statement of the existing scope |
| **Demonstrated behavior** | A particular scenario has been reproduced | An accessible demo, repeatable walkthrough or other verifiable result |
| **In development** | The architecture has been defined but is not an end-to-end supported behavior | Explicit identification as work in progress |
| **Design direction** | An intended principle or target awaiting implementation or validation | Clear conceptual framing; no deployment promise |
| **Not established** | A property has not been independently evaluated | No performance, security or parity claim |

The current public notes avoid publishing private test artifacts or release details. A broad label such as "implemented foundation" should never be read as proof that the complete end-to-end product has that behavior.

## What is fair to say

Artemis has an existing product/demo experience, capability and execution foundations, context/memory components, and prior work on governance and UI. A separately published [MCP Event Intelligence project](https://github.com/sarooo17/event-intelligence) explores durable temporal conditions.

The more ambitious unified Workspace, front-desk control plane, globally addressable concurrent Executions, dynamic context per operation, Cases and runtime-owned continuation architecture are described here as **vNext targets**, unless a specific behavior is separately demonstrated.

The public EI package's capabilities must not be conflated with capabilities fully integrated or deployed in Artemis itself. Its own repository and license govern that project.

## Claims this repository does not make

- That the complete vNext architecture is in production.
- That the product supports every provider, ERP or business workflow.
- That Artemis is uniquely capable of persistence, memory, automation or generated UI.
- That Artemis is more secure, faster or less expensive than a named competitor without reproducible comparisons.
- That a model explanation is equivalent to authoritative business verification.
- That a demo interaction establishes enterprise production readiness.

## What a stronger public evidence program could include

With suitable privacy and security review, future releases could provide sanitized task walkthroughs, dated capability availability notes, reproducible scenario tests and measured trade-offs.

A credible comparison should always distinguish **what was designed**, **what was implemented**, **what was actually tested** and **what was observed**.

## Publication boundaries

The repository intentionally excludes proprietary source, deployment topology, sensitive policy implementation, internal schemas, model-routing internals, credential handling, customer information and detailed security test procedures.

See [Architecture status](STATUS.md), [Architectural trade-offs](ARCHITECTURAL-TRADEOFFS.md) and the [interactive demo](https://demo.underlay.studio).
