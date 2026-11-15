# Evidence and verification

[Return to README](../README.md)

## A claim needs an observable basis

A useful diagnostic result is a bounded claim supported by an observation. A check definition should state its criterion before interpreting the observation. Otherwise the same response could be labeled successful merely because it arrived, even if it failed the task the person intended.

Future reports could distinguish direct observations, conclusions derived from those observations, and user-supplied context. Each source has different limits. An installed tool is not evidence that it runs. A running process is not evidence that its service is reachable. A response is not evidence that a state change persisted.

## An evidence record in prose

A human-inspectable record could identify the target, method, observing environment, start and finish times, relevant definition revision, expected condition, observed condition, and evidence origin. It should also describe time limits, missing information, redactions, and whether another observer could repeat the check. A report can be inspectable without exposing credentials or private content.

Evidence freshness should depend on the claim. An endpoint response may become outdated immediately; a hardware inventory may change less frequently. There is no proposed universal expiration period. Reports should explain their chosen freshness assumptions and avoid presenting a cached observation as a new attempt.

## Verification strength

| Claim | Evidence that could support it | What it would not establish |
|---|---|---|
| A selected endpoint responded | An exchange with identity, timing, and protocol context | Availability from every region or at a later time |
| A declared write persisted | Consent and scope, operation identity, and independent readback matching the intended result | Permissions for unrelated resources or future writes |
| Stored data matches an expected copy | A comparison against a trustworthy reference with provenance | Integrity when both the data and reference were compromised |
| A backup supports a specific restore | An authorized restoration exercise in an isolated target, with application-level checks | Recovery under every disaster scenario |
| A diagnostic result is repeatable | Repeated observations under documented conditions | Complete independence when all observations share the same failure source |

Independent readback should mean observing the resulting state through a distinct retrieval step, not echoing the submitted request. The report should disclose when the readback shares a cache, authority, or infrastructure with the original operation. Repetition improves some confidence but cannot remove common-source errors.

## Privacy and public sharing

Evidence may reveal account identifiers, internal addresses, filenames, database contents, service topology, or device information. A future checker should collect only what its question requires, avoid recording secrets, and offer a preview before export. Redactions should be visible so readers know when they cannot independently examine a detail. Redaction should not silently strengthen the conclusion.

An observation intended for a private diagnostic session is not automatically suitable for a public issue. This public concept repository should contain hypothetical examples and deliberately selected source references, never captured credentials or private diagnostic dumps.

## Failed and interrupted operations

Failures, timeouts, cancellation, cleanup attempts, and unresolved state changes belong in the record. A proposed temporary transaction should disclose what it creates, how it is identified, whether cleanup is authorized, and how cleanup would be checked. An unsuccessful cleanup must not disappear behind a successful primary check.

UCE-001 performs no diagnostic experiments. Its document and publication checks are repository administration evidence, not evidence of an implemented UCE engine. See the [contract](UNIVERSAL-DIAGNOSTIC-CONTRACT.md) and [project status](PROJECT-STATUS.md).
