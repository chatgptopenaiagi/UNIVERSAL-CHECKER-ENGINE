# Universal checker blueprint

[Return to README](../README.md)

## A reusable conceptual template

A future checker definition could serve as an agreement between domain experts, implementers, interface designers, and people interpreting reports. The agreement would describe a diagnostic question and the evidence needed to answer it. UCE-001 proposes the following template only in prose; no executable definition format is supplied.

| Building block | What a future definition should explain |
|---|---|
| Identity and scope | Checker name, revision, domain, target, intended users, and explicit exclusions |
| What to check | One or more precise questions and the criteria that would answer them |
| How to check it | Proposed observation method, prerequisites, dependencies, time limits, and resource budget |
| Platform capabilities | Required interfaces, permissions, hardware access, and expected unsupported cases |
| Consent | External communication, sensitive information, changes, costs, and cancellation implications |
| How to classify results | The connection between observations and the shared vocabulary, including ambiguous cases |
| How to verify evidence | Provenance, expected reference, freshness, independent observation, and limitations |
| How to explain results | Plain-language consequence, expert detail, and justified next investigations |
| Reporting and retention | Evidence to include, redact, preserve, export, or discard |
| Operation lifecycle | Dependencies, partial completion, retries, unresolved changes, and consented cleanup |
| Evolution | Definition compatibility, deprecation, and treatment of reports produced under earlier meanings |

## Hypothetical application: backup readiness

The question “Can this backup restore the intended application state?” is broader than “Does a backup file exist?” A definition could separate existence, expected inventory, integrity comparison, isolated restoration, and application-level validation. Each question would have its own evidence and limits.

Without an authorized restoration environment, restoration readiness could remain NOT_TESTED even if inventory and integrity checks succeed. This explicit separation is a reusable design principle. The storage interface, database recovery process, and application validation method would remain specific to the actual backup system.

## Possible engineering reuse

A shared specification might reduce repeated design work for result wording, evidence descriptions, coverage summaries, and consent interactions. Independent teams could compare their interpretations against the same written scenarios. That possibility does not establish a functioning module system, interchange format, or compatibility test suite.

The strongest early experiment would ask which parts two independently designed checkers can share without erasing useful distinctions. A common definition is valuable only if it makes implementations and reports more accurate or easier to understand.

## Obstacles to a universal implementation

Operating systems expose different interfaces and privilege boundaries. Services vary in error semantics, identity models, rate limits, and transaction guarantees. Hardware may hide telemetry or require vendor-specific access. Network observations depend on route, location, proxy, and timing. A shared specification cannot grant missing permission or recover evidence an environment does not expose.

Accordingly, the proposal is a reusable blueprint for independent checkers. It does not claim that one universal implementation could perform every possible diagnostic operation. See [architecture](UNIVERSAL-ARCHITECTURE.md), [limitations](LIMITATIONS-AND-CHALLENGES.md), and [future research](FUTURE-ROADMAP.md).
