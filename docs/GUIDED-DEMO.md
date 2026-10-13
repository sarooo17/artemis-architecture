# Explore the Artemis demo

**Open the interactive preview:** [demo.underlay.studio](https://demo.underlay.studio)

This is a product preview, **not a public test environment for every vNext architectural concept in this repository**. Available features, data and permissions may change over time. Do not use production credentials or sensitive real business information in a demo environment.

## Three questions to explore

The examples below are **suggested evaluation themes**, not assertions that each workflow is available or has passed an end-to-end test in the current demo.

### A. An operational question that crosses records

**Question to investigate:** What is preventing a particular order from advancing?

Look for whether the experience helps you inspect relevant business records and understand the source of its answer, rather than producing a plausible narrative disconnected from the business system.

**Architecture behind the question:** [semantic capabilities](02-CAPABILITY-FABRIC.md), [world interactions](18-SEMANTIC-WORLD.md), [evidence and verification](07-AUTHORITY-AND-VERIFICATION.md).

### B. From information to governed action

**Question to investigate:** If a task implies changing a business record, how does the system distinguish analysis from the right to act?

Look for boundaries between viewing a result, proposing an action, obtaining appropriate authorization and verifying a consequential effect. **The current ERP-backed demonstration should be treated as read-oriented; do not assume that final ERP changes are enabled.**

**Architecture behind the question:** [authority and verification](07-AUTHORITY-AND-VERIFICATION.md), [interaction vs. execution](15-FRONT-DESK.md).

### C. Work across time

**Question to investigate:** What would it take for an investigation to wait for a future document, event or approval, then resume without restarting its reasoning from a conversation transcript?

This is primarily a **vNext architectural walkthrough**, not a promise that the current demo exposes the full Event Intelligence / Execution continuation lifecycle.

**Architecture behind the question:** [Event Intelligence](03-EVENT-INTELLIGENCE.md), [durable work](01-WORK-AS-THE-PRIMITIVE.md), [cases and automation](12-CASES-AND-AUTOMATION.md).

## How to interpret what you see

- **A live interaction** demonstrates only the behavior you can actually reproduce.
- **An architecture note** explains a design principle; it is not a feature availability claim.
- **A proposed end-to-end scenario** illustrates intended behavior and may require features that are still in development.
- **A successful textual answer** is not proof that any business-side action occurred.

For a summary of the development boundary, see [Architecture status](STATUS.md) and [Evidence and limitations](EVIDENCE-AND-LIMITATIONS.md).

**Other links:** [Underlay](https://underlay.studio) · [Engineering memos](https://memos.underlay.studio)
