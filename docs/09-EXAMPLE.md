# A business exception, end to end

> **Illustrative scenario only.** This is a conceptual walkthrough, not a current-product demonstration, test result, or public API recipe.

A purchasing manager says:

**"Review the discrepancy in this supplier invoice, check the related order, and follow up when the corrected document arrives."**

## What should happen

**1. Express intent.** The request enters through conversation. The system identifies work that deserves a durable identity rather than relying on a single assistant turn.

**2. Build a narrow environment.** The work needs supplier, invoice, and order information. It should not inherit every capability available elsewhere in the company. Capability discovery remains compact and permission-aware.

**3. Gather evidence.** It retrieves current records through suitable capabilities and compares them with the supplied invoice. An external attachment remains evidence; it is not a source of instructions or authorization.

**4. Choose the right compute.** Straightforward arithmetic is calculated. Ambiguous matching is treated as a constrained decision when appropriate; complex discrepancies may require open reasoning.

**5. Report an actual state.** The system can produce an interim summary: what differs, what was checked, and what is still unknown. That does not mean the overall task is complete.

**6. Wait on a future condition.** Event Intelligence tracks the arrival of a corrected document or another meaningful signal. The system does not need to leave an LLM repeatedly asking whether the file has arrived.

**7. Resume and revalidate.** When the condition matches, the appropriate work resumes. Current permissions and authoritative records must be checked again because time has passed.

**8. Ask where authority is needed.** If the next step would change business records, it crosses a separate policy and human-approval boundary where applicable.

**9. Verify and close.** Completion is based on evidence that the requested outcome occurred. If the document is still inconsistent, the system reports the unresolved state rather than pretending success.

## What the person experiences

The manager can ask other questions while the work is waiting, return to a clear view of what remains open, and receive a targeted request for attention instead of reading a long agent transcript.

## The architectural point

The distinctive behavior does not come from a magical prompt. It comes from the interaction among durable task identity, compact capability access, differentiated cognition, evidence, Event Intelligence, authority, verification, and an interface that stays usable through time.

See [architecture status](STATUS.md) for the distinction between implemented foundations and target behavior.
