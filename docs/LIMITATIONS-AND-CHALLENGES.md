# Limitations and challenges

[Return to README](../README.md)

## Universal concepts do not imply universal access

No implementation can be assumed to inspect every operating system, service, device, or application. Interfaces may be unavailable, permissions may be insufficient, and relevant state may be inaccessible by design. A future checker should state those boundaries instead of inferring success or failure from missing evidence.

Windows, Android, hosted services, containers, and hardware runtimes offer different kinds of visibility. Shared conceptual interfaces can describe intent and results, but cannot eliminate platform adapters or expert knowledge. Python in the architecture is an implementation possibility, not a guarantee of portability.

## Meaning, causality, and coverage

A shared word can conceal very different claims. VERIFIED must identify what was verified and how. A response from a website is not equivalent to a successful recovery from backup. A diagnostic symptom may have several causes, and correlation between failed checks may reflect a shared dependency rather than independent corroboration.

Every finite session has incomplete coverage. Sampling, selected endpoints, unavailable privileges, and time limits constrain conclusions. Aggregation must preserve omissions. A security review cannot prove that no vulnerability exists, and a small GPU workload cannot prove stability for every workload.

## Time and observer effects

Conditions can change between prerequisite checks and later operations. A permission observation may be outdated by the time a write is attempted. A timeout may leave an operation in an unknown state. Retries can duplicate changes; measurement itself can create load or affect resource availability.

Future designs would need bounded work, cancellation behavior, rate-limit awareness, and careful accounting for partial completion. None of those controls is implemented here.

## Trust and evidence limitations

Provider status pages, device telemetry, logs, and API responses may be incomplete or misleading. Independent retrieval can improve confidence while still sharing an underlying source of failure. Integrity comparisons are only as trustworthy as the reference and observation process.

Reports can also be fabricated or misinterpreted. A common format would not itself certify authenticity or correctness. Evidence provenance, privacy-preserving review, and trust in independently developed extensions remain unresolved research topics.

## Human and organizational constraints

Terminology may not translate cleanly. Accessible interfaces need evaluation with actual users and devices. Beginners may interpret a partial success as a guarantee; experts may need details that complicate the summary. A single interface cannot assume a single audience or level of expertise.

Maintainers would need to track changing APIs, platform permissions, hardware interfaces, and diagnostic definitions. Governance, licensing, funding, and compatibility policy require decisions that this conceptual foundation does not make.

## Scope boundary

UCE-001 establishes documentation, not feasibility, interoperability, performance, accessibility compliance, or diagnostic accuracy. Any later claim of those properties would require scoped evidence from actual work. Related: [open research questions](OPEN-RESEARCH-QUESTIONS.md), [evidence](EVIDENCE-AND-VERIFICATION.md), and [roadmap](FUTURE-ROADMAP.md).
