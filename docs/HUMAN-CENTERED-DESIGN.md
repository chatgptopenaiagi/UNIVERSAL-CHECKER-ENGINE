# Human-centered design

[Return to README](../README.md)

## One button, meaningful scope

A future main action could start a clearly described set of ordinary checks. Before it begins, the interface should identify the selected target, expected duration, whether information leaves the device, and any material resource use. Simplicity depends on sensible scope and language, not on hiding consequential operations.

The session could show progress per check, permit cancellation, and display completed observations as they become available. Cancellation would leave unstarted checks NOT_TESTED and explain any in-flight operation whose final outcome remains unknown.

## Results people can understand

Each result could provide a short statement, its practical consequence, and an expandable explanation. A hypothetical message might say: “The service responded, but it did not accept the supplied identity. Repository write access was not tested.” This is more useful than a single red indicator because it distinguishes a working connection from an identity problem.

Experts could inspect timings, scope, platform limitations, and redacted evidence without making those details prerequisites for beginners. Recommendations should distinguish a supported conclusion from a possible cause and should identify the expected effect of any suggested action.

## Visual and accessible communication

Status indicators should pair text with shapes or icons rather than rely on color alone. Keyboard navigation, focus visibility, screen-reader labels, scalable text, adequate contrast, and predictable reading order would need deliberate design and evaluation. Progress updates should avoid overwhelming assistive technologies. Motion should be optional where possible.

Accessible diagnostic communication also includes understandable wording, explicit units and dates, and summaries that do not turn technical uncertainty into apparent user error. Device-specific accessibility conventions would need native evaluation; shared principles alone cannot prove accessibility.

## Languages and levels of detail

Stable classification meanings could coexist with translated user-facing labels. Translations should preserve differences such as authentication versus permission and should be reviewed for technical meaning. Original diagnostic text could remain available alongside an explanation when safe. Locale-sensitive times and number formats should retain enough context for an expert in another locale to interpret exported evidence.

Beginners could receive task-oriented guidance. Experts could select advanced checks and inspect assumptions. Advanced mode should disclose additional permissions, cost, privacy implications, and potential side effects; it should not silently bypass consent.

## Consent and evidence transparency

Read-only observations can still contact external systems or disclose metadata. The initial scope should explain those effects. State-changing actions would require specific consent identifying the target, intended change, expected verification, and cleanup responsibilities. A general “check everything” button would not authorize repository writes, database changes, restoration over existing data, permission changes, or intrusive scanning.

Users should be able to inspect what will be shared, remove optional evidence, and understand how removal limits verification. No telemetry, centralized account, or cloud report service is assumed by the concept. Retention, deletion, offline use, and export behavior remain design questions.

The goal is reduced confusion between humans and digital systems. See [philosophy](VISION-AND-PHILOSOPHY.md), [evidence](EVIDENCE-AND-VERIFICATION.md), and [research questions](OPEN-RESEARCH-QUESTIONS.md).
