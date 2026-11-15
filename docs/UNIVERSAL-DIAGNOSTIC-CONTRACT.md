# Universal diagnostic contract

[Return to README](../README.md)

## Status and scope

This is a proposed human-readable specification for future discussion. It is not a software schema, executable validator, implemented protocol, or settled standard. Its purpose is to keep conclusions tied to questions and evidence.

A future result should describe the checker and definition revision, the question asked, the target and scope, relevant platform capabilities, observation time and duration, prerequisites, consent where applicable, collected evidence, classification, limitations, and a plain-language explanation. Sensitive identifiers should be minimized or redacted. These are conceptual information requirements, not machine field definitions.

## Proposed classifications

| Classification | Meaning within a declared scope | Evidence needed and limits |
|---|---|---|
| CONNECTED | A named communication path reached the expected endpoint at a stated layer | A completed exchange with endpoint identity and timing where available; transport success alone proves neither identity acceptance nor permission |
| DISCONNECTED | The declared connection attempt did not establish the required path | Attempt details and a specific connection failure; it does not prove that every route or the entire service is unavailable |
| AUTHENTICATED | The intended service accepted an identity using the selected mechanism | A trusted identity response or session confirmation tied to the target; merely possessing a credential is insufficient |
| UNAUTHENTICATED | No accepted identity was established for an authentication attempt | An explicit rejection or established absence of an authenticated session; if no authentication attempt was made, report NOT_TESTED for that check |
| AUTHORIZED | The identity has permission for a specific action on a specific resource | An authoritative permission decision or an operation demonstrating that exact permission; account membership or a broad token scope alone is insufficient |
| PERMISSION_DENIED | The specific action was explicitly denied by the relevant authority | A permission rejection linked to the attempted action and resource; ambiguous errors, concealed resources, and rate limits need additional interpretation |
| VERIFIED | A declared claim satisfied its stated verification criterion | An independent observation or readback appropriate to the claim, with expected and observed properties compared; never a blanket assurance of system health |
| FAILED | A completed check established that a stated success criterion was not met | The criterion, observed mismatch, and supporting evidence; checker faults must be distinguished from target faults |
| TIMEOUT | The observation window expired before a decisive outcome | The limit, elapsed time, and last known stage; the remote operation may still have completed |
| UNSUPPORTED | The required diagnostic capability is not available in the declared environment or checker | A capability assessment and reason, such as an unavailable interface; permission denial alone does not mean the platform lacks support |
| NOT_TESTED | The check was not attempted | A reason such as user decline, missing prerequisite, exclusion from scope, or cancellation before starting; absence of execution is not failure evidence |
| UNKNOWN | Available evidence does not support a reliable classification | The incomplete, conflicting, inaccessible, or ambiguous observations and their limits; this is an explicit uncertainty result |

## Dimensions rather than a single ladder

**CONNECTED IS NOT THE SAME AS AUTHENTICATED. AUTHENTICATED IS NOT THE SAME AS AUTHORIZED. AUTHORIZED IS NOT THE SAME AS VERIFIED.**

These terms answer different questions. They are not necessarily mutually exclusive labels for an entire session. A report could contain a CONNECTED reachability finding, an AUTHENTICATED identity finding, and a PERMISSION_DENIED write finding. A verification could establish a narrow claim about a public resource without any authenticated identity.

The eventual representation of multiple dimensions remains open. Every classified finding should identify its question, avoiding combinations whose meaning depends on an undocumented ordering. Successful child checks must not erase unsuccessful or unattempted ones.

## Hypothetical interpretation examples

A service responds over HTTPS, but rejects the supplied identity: reachability is CONNECTED, authentication is UNAUTHENTICATED, and a protected operation may be NOT_TESTED. A credential should never appear in the evidence report.

An identity is accepted and an authoritative permission response allows writing to a selected repository: identity is AUTHENTICATED and the scoped permission is AUTHORIZED. A transaction that was never attempted remains NOT_TESTED. VERIFIED would require a defined operation and adequate readback, not merely permission.

A write request times out. The action's outcome remains UNKNOWN unless a later independent observation resolves it. Blindly repeating the write could create duplicates. The timeout belongs to the attempt; a subsequent verified readback should be recorded separately, preserving the earlier uncertainty and timestamps.

A target returns an ambiguous “not found” response. This alone may not distinguish absence from deliberately concealed access. The explanation should preserve that ambiguity instead of inventing PERMISSION_DENIED or VERIFIED absence.

## Rules for explanations and aggregation

Every explanation should answer what was checked, what happened, what evidence supports the interpretation, what remains unproven, and what next action is justified. Severity, confidence, and task impact are separate considerations from classification; a successful connection can coexist with a critical failure elsewhere.

A session summary should report coverage and unresolved findings. “All attempted checks satisfied their criteria” must not imply that excluded, unsupported, or unattempted checks succeeded. Stale results should retain their original observation time and should not describe a current condition without renewed evidence.

Related: [evidence](EVIDENCE-AND-VERIFICATION.md), [human-centered design](HUMAN-CENTERED-DESIGN.md), and [limitations](LIMITATIONS-AND-CHALLENGES.md).
