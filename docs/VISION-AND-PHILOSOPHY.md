# Vision and philosophy

[Return to README](../README.md)

## Technology should explain its condition

People encounter systems through tasks: reaching a service, opening a repository, running an application, or recovering information. Failure messages often describe an internal mechanism without explaining whether the intended task is possible. UCE proposes diagnostics organized around human understanding, with technical detail available to support the conclusion.

The guiding principle is **ONE ACTION. MANY CHECKS. VERIFIABLE EVIDENCE. HUMAN UNDERSTANDING.** The button is the entry point; the value lies in the accuracy, limits, and usefulness of the explanation that follows.

## Independence and shared meaning

A checker should answer a bounded question. A successful network check must not silently stand in for an authentication check. An unavailable optional tool must not invalidate unrelated evidence. When one check depends on another, that dependency should be visible; independent work could continue when it remains meaningful.

Shared language could reduce the effort required to learn each new checker. Shared language must also preserve domain differences. A website response, a database transaction, and a restored file provide different kinds of evidence even when their summaries use the word VERIFIED.

## Honesty about uncertainty

UNKNOWN, NOT_TESTED, and UNSUPPORTED should be useful outcomes rather than embarrassing gaps to conceal. No observation is better than an invented success. A time limit should describe the observation window, not imply certainty about a permanent outage. A result should state its target, time, and scope because system conditions change.

Suggestions should follow from evidence. A diagnosis may support a next investigation without supporting an automatic repair. The user should be able to understand why an action is suggested and what it might change.

## Human agency

One button should reduce repetitive interaction, not erase consent. The ordinary session could perform disclosed, bounded observations. Writes, permission changes, expensive workloads, restoration attempts, and intrusive scans would require an explicit scope and appropriate consent. Users should be able to decline, cancel, inspect, and share only the information they choose.

The long-term aspiration is many independent checkers that are easier to understand and harder to mistake for broader guarantees. Whether common conventions can achieve that is a research question. See [human-centered design](HUMAN-CENTERED-DESIGN.md) and [limitations](LIMITATIONS-AND-CHALLENGES.md).
