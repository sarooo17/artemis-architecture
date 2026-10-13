# Capabilities, skills, knowledge and governed learning

> **Design thesis:** what a system *can do*, *knows how to do*, *knows about*, and *remembers* are different things.

These concepts are often collapsed into a prompt, a giant tool collection or an undifferentiated memory store. Artemis's design keeps them separate so the runtime can compose an effective environment without confusing instructions with facts or rights.

## Distinct responsibilities

| Concept | What it contributes |
| --- | --- |
| **Capability** | A meaningful operation available through a governed execution boundary |
| **Skill** | A reusable method or procedure for approaching particular work |
| **Specialist** | An expertise profile useful for a class of tasks |
| **Agent Blueprint** | A reusable configuration of goals, preferred expertise and resources |
| **Knowledge Source** | An inspectable corpus of reference material, with scope and provenance |
| **Memory** | Reusable information retained for a user or organization under governance |

For example, accessing purchase orders is a capability; a supplier-onboarding procedure is a skill; a company policy manual is knowledge; a preference for PDF reports may belong in user memory.

One does not grant the powers of another. A document describing an approval process is not itself an approval. A memory of a past action is not current authority.

## Skills and agents are not just prompt files

A reusable Skill may combine instructions with templates, procedural steps, schemas or governed executable resources. For example, an invoice-reconciliation method might define both a workflow and how to validate its output. A Skill is narrower than an entire business domain; **finance** is a domain, while a repeatable three-way matching procedure is a Skill.

An **Agent Blueprint** describes a reusable user- or company-scoped worker configuration. A **Worker Profile** is the task-specific environment assembled when actual work runs. A blueprint is not a permanently active process and cannot itself grant new business permissions.

The architecture aims to let company-defined skills and agent configurations participate in the same governed composition process as system-provided ones. Lifecycle, access and evidence requirements still apply.

## On-demand rather than everything at startup

The target avoids injecting every instruction, company file or remembered fact into every model request. A task can discover relevant skills, retrieve appropriate reference material, and request additional context as the problem develops.

This is another way the environment can evolve during work without becoming an unbounded prompt.

## Learning should propose, not silently rewrite the system

Repeated corrections and successful patterns may suggest reusable improvements. But Artemis does not aim to convert every repeated behavior into a new policy, skill or permanent agent configuration automatically.

The target lifecycle is **observe → propose → evaluate → review → version → activate**, with appropriate governance and rollback. A person's preference must not silently become a company-wide rule.

## The limit of the public note

Internal selection algorithms, asset schemas, evaluation criteria and promotion mechanisms are not published here.

**Status:** existing skills, memory and capability components provide foundations; the integrated blueprint, knowledge-source and governed-learning model is an architectural target. See [Status](STATUS.md).
