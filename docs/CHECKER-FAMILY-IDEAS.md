# Checker family ideas

[Return to README](../README.md)

All twelve profiles describe potential future applications. None is implemented in UCE-001. Evidence examples are proposals, not collected results. Each checker would need its own scope, capability assessment, consent model, and domain expertise while following the [shared contract](UNIVERSAL-DIAGNOSTIC-CONTRACT.md).

## 01. GitHub Checker

- **Purpose:** Explain whether a selected GitHub task can proceed, separating connectivity, identity, repository access, Git operations, and verified transactions.
- **Potential users:** Developers, repository owners, educators, support staff, and people unfamiliar with Git tooling.
- **Problems it could solve:** Confusion between a reachable API and an accepted credential; between repository read access and write permission; or between a successful local commit and a published remote commit.
- **Conceptual diagnostic categories:** DNS and HTTPS reachability, API availability, authentication, scoped authorization, repository accessibility, local Git capability, fetch/push prerequisites, and separately consented transaction verification.
- **Possible evidence:** Endpoint responses, accepted identity, permission observations, repository metadata, local and remote object identifiers, and independent readback of a specifically authorized transaction. Secrets and private repository content would require protection.
- **Platform-specific limitations:** Mobile environments may lack local Git tools; enterprise hosts and proxies may differ; service rate limits can interrupt observations; unavailable private resources can be ambiguous. A successful API request does not establish that local Git transport works.
- **Potential ecosystem contribution:** A concrete vocabulary for the distinction between connection, authentication, permission, and verified persistence, informed conceptually by GTB without importing its implementation.

## 02. Internet Checker

- **Purpose:** Explain the observed condition of selected internet paths and services.
- **Potential users:** Home users, remote workers, support teams, network administrators, and travelers.
- **Problems it could solve:** Uncertainty about whether an apparent outage relates to DNS, the local network, a selected route, HTTPS, or intermittent degradation.
- **Conceptual diagnostic categories:** Connectivity, DNS resolution, latency, routing observations, HTTPS availability, packet loss where observable, and reliability over a declared interval.
- **Possible evidence:** Resolver answers, selected endpoint exchanges, timing distributions, route observations where permitted, and timestamped successes and failures. The vantage point and selected destinations should be explicit.
- **Platform-specific limitations:** Mobile restrictions, VPNs, captive portals, proxies, and filtered diagnostic traffic affect interpretation. Missing route responses do not necessarily mean a path is broken. A few reachable destinations cannot prove universal internet availability.
- **Potential ecosystem contribution:** Principles for time-bounded measurements, partial reachability, and environment-dependent observations that other online checkers could reuse.

## 03. Windows Checker

- **Purpose:** Help people understand selected aspects of Windows operating-system and device condition.
- **Potential users:** PC owners, help desks, administrators, and technicians.
- **Problems it could solve:** Difficulty distinguishing an unavailable service, a device or driver problem, an update issue, and a symptom whose cause remains unknown.
- **Conceptual diagnostic categories:** Operating-system health indicators, service state, hardware inventory, driver status, update state, resource pressure, and system diagnostic records.
- **Possible evidence:** Version and update observations, service responses, device status, selected event records, resource measurements, and supported integrity-check outcomes, each with scope and collection time.
- **Platform-specific limitations:** Editions, versions, architectures, administrative privileges, policy, and vendor interfaces differ. A stopped service may be intentional. Repair operations, reboots, and configuration changes would require separate authorization.
- **Potential ecosystem contribution:** A model for capability discovery and explaining privilege-dependent results without presenting missing permissions as evidence of a broken system.

## 04. Android Checker

- **Purpose:** Explain selected device capabilities and application-accessible aspects of Android health.
- **Potential users:** Device owners, mobile support staff, application testers, and accessibility testers.
- **Problems it could solve:** Confusion about storage pressure, connectivity, missing sensor access, denied application permissions, or restricted background behavior.
- **Conceptual diagnostic categories:** Storage, network connectivity, device sensors, application permissions, supported battery or resource observations, and exposed system-health indicators.
- **Possible evidence:** Permission decisions, accessible storage measurements, selected connectivity exchanges, sensor availability and bounded sample observations, and platform-reported condition indicators.
- **Platform-specific limitations:** Sandboxing, manufacturer variation, OS version, managed-device policy, and background restrictions limit visibility. Emulator findings do not establish physical-device behavior. Sensor presence does not prove calibration or accuracy.
- **Potential ecosystem contribution:** Clear treatment of constrained environments, permission explanations, and the difference between unavailable evidence and unhealthy hardware.

## 05. AI Checker

- **Purpose:** Describe the operational readiness of selected AI models, local runtimes, and inference endpoints.
- **Potential users:** Model operators, developers, researchers, support engineers, and users of local AI tools.
- **Problems it could solve:** Uncertainty about whether a model is listed, accessible, compatible with a requested operation, or actually able to complete a bounded inference request.
- **Conceptual diagnostic categories:** Model availability, endpoint reachability, authentication, scoped access, request compatibility, response time, runtime capability, and operational failures.
- **Possible evidence:** Model identifiers and revisions, capability responses, redacted request metadata, bounded synthetic inference outcomes, timing, and resource observations. A local installation alone would not establish successful inference.
- **Platform-specific limitations:** Providers differ in API semantics, quotas, cost, and model versions; local models depend on memory and runtime support. Nondeterminism complicates exact comparisons. Successful inference does not establish answer correctness, safety, or general model quality.
- **Potential ecosystem contribution:** A disciplined distinction between availability, compatibility, successful execution, and evaluation of content quality, with explicit budgets and data handling.

## 06. Database Checker

- **Purpose:** Explain whether a specific database interaction is reachable, permitted, and supported by appropriate integrity evidence.
- **Potential users:** Database administrators, application developers, operators, and support teams.
- **Problems it could solve:** Confusion between an open connection and usable query access, or between a completed query and a consistency or integrity guarantee.
- **Conceptual diagnostic categories:** Connectivity, authentication, scoped query permission, bounded query execution, availability, replication or consistency observations, and integrity verification.
- **Possible evidence:** Connection outcomes, accepted identity, safe query results, transaction identifiers where available, replica observations, and engine-supported integrity reports. Sensitive rows should not become diagnostic exports by default.
- **Platform-specific limitations:** Engines have different transaction and consistency models; managed services restrict inspection; queries can impose load or locks. Sampled records cannot prove global consistency. Any write-based verification would need an explicit isolated target and consent.
- **Potential ecosystem contribution:** Precise reporting of query scope, transaction state, load, and the difference between successful execution and correctness of stored information.

## 07. Security Checker

- **Purpose:** Support defensive understanding of a specifically authorized system's observable security configuration.
- **Potential users:** System owners, administrators, security teams, and people reviewing their own devices or services.
- **Problems it could solve:** Unclear authentication settings, unexpected exposure, missing defensive controls, or misleading claims that a system is “secure” because a small checklist passed.
- **Conceptual diagnostic categories:** Security configuration, authentication mechanisms, exposure indicators, permission boundaries, patch-related observations, and defensive diagnostic coverage.
- **Possible evidence:** Authorized configuration observations, negotiated connection properties, relevant control status, and scoped exposure findings with collection method and timestamp.
- **Platform-specific limitations:** Privileges, network position, policy, and third-party boundaries restrict visibility. A passing check cannot prove absence of compromise or vulnerabilities. Intrusive probes and scanning outside an owned or authorized scope are not implied by a diagnostic request.
- **Potential ecosystem contribution:** Explicit threat and observation scope, careful negative claims, and consent principles applicable to all checkers.

## 08. Cloud Checker

- **Purpose:** Explain the accessibility and observed condition of selected cloud resources and services.
- **Potential users:** Cloud administrators, developers, platform teams, and support engineers.
- **Problems it could solve:** Confusion between control-plane API availability, accepted credentials, resource permissions, and actual workload availability.
- **Conceptual diagnostic categories:** API connectivity, identity, resource authorization, service availability, resource inventory, quotas where accessible, and infrastructure or workload status.
- **Possible evidence:** Scoped identity responses, permission observations, resource descriptions, provider status information, regional observations, and bounded workload responses. Provider-reported status should be labeled as a distinct evidence source.
- **Platform-specific limitations:** Providers differ in regions, identity systems, consistency, billing, and API behavior. A functioning control plane does not prove a functioning data plane. Queries or probes may incur costs and should have declared budgets.
- **Potential ecosystem contribution:** Separation of provider assertions from direct observations and consistent explanations of account, region, resource, and workload scope.

## 09. Storage Checker

- **Purpose:** Explain available storage capacity and observable signs of device, filesystem, and data condition.
- **Potential users:** Device owners, storage administrators, creators managing large files, and support staff.
- **Problems it could solve:** Confusion between free capacity, filesystem usability, device health telemetry, and integrity of particular data.
- **Conceptual diagnostic categories:** Capacity, mount or volume availability, device health, filesystem diagnostics, access permissions, and comparison against known data-integrity references.
- **Possible evidence:** Capacity observations, supported device telemetry, filesystem reports, read outcomes, and comparisons with trusted checksums or reference copies.
- **Platform-specific limitations:** Virtual disks, USB bridges, mobile sandboxes, and storage controllers may hide telemetry. A readable file is not necessarily correct, and a healthy indicator is not a prediction that hardware cannot fail. Repairs and intensive workloads need separate consideration and consent.
- **Potential ecosystem contribution:** Distinguishing physical, logical, and content-level evidence while reporting uncertainty when lower layers are inaccessible.

## 10. Backup Checker

- **Purpose:** Explain what evidence supports the readiness of a selected backup for a defined recovery objective.
- **Potential users:** Individuals, administrators, backup operators, and teams responsible for continuity.
- **Problems it could solve:** False confidence from a successful backup job or visible archive when required files, decryption material, dependencies, or restoration procedures are missing.
- **Conceptual diagnostic categories:** Existence, expected coverage and completeness, freshness, integrity, dependency availability, and restoration readiness.
- **Possible evidence:** Backup inventory, expected-source comparison, job records labeled as reported evidence, integrity comparisons, and explicitly authorized isolated restoration results with application checks.
- **Platform-specific limitations:** Encryption, retention, provider access, storage cost, and application consistency constrain verification. A sample restore supports only its tested scope. Production overwrite or restoration over user data is not an ordinary one-button check.
- **Potential ecosystem contribution:** A clear hierarchy of claims from existence through restoration evidence, without collapsing all stages into a single “backup good” result.

## 11. Website Checker

- **Purpose:** Explain whether selected website pages and user journeys are reachable and exhibit expected observable behavior.
- **Potential users:** Site owners, developers, support teams, accessibility reviewers, and publishers.
- **Problems it could solve:** Confusion between an HTTP response, a rendered page, an accessible interaction, and a functioning application journey.
- **Conceptual diagnostic categories:** Availability, HTTPS certificate observations, response times, redirects, selected application-health checks, and accessibility observations.
- **Possible evidence:** Response metadata, certificate chain and identity observations, timing, selected rendered-page findings, and bounded interaction outcomes. Accessibility findings would identify their method and coverage.
- **Platform-specific limitations:** Geography, content delivery caches, authentication, browser differences, and client-side execution alter results. Automated observations cannot establish complete accessibility. Purchasing, submitting forms, or changing accounts would require explicit consent and scope.
- **Potential ecosystem contribution:** Separation of transport, presentation, interaction, and accessibility findings, with honest coverage reporting.

## 12. GPU Checker

- **Purpose:** Explain whether a selected graphics device and computing environment can support a declared operation.
- **Potential users:** Researchers, AI developers, creators, workstation owners, and support engineers.
- **Problems it could solve:** Confusion between detected hardware, installed drivers, exposed computing capability, available memory, and actual successful execution.
- **Conceptual diagnostic categories:** Hardware detection, driver compatibility, graphics or compute interface availability, memory observations, runtime compatibility, and bounded operational diagnostics.
- **Possible evidence:** Device and driver identifiers, reported capabilities, accessible memory observations, runtime initialization outcomes, and results from a specifically approved bounded workload.
- **Platform-specific limitations:** Vendors, operating systems, containers, virtual machines, mobile devices, and permissions expose different interfaces. Shared memory can change during observation. An installed runtime does not prove usable hardware acceleration, and a small workload does not establish stability under sustained load.
- **Potential ecosystem contribution:** Evidence distinctions between inventory, initialization, execution, and workload-specific validation that would also benefit AI and system checkers.

## Shared research opportunity

These profiles repeatedly need scope, freshness, permissions, uncertainty, and explanations. Their actual observation methods remain different. The [blueprint](UNIVERSAL-CHECKER-BLUEPRINT.md) asks what can be reused, while the [roadmap](FUTURE-ROADMAP.md) keeps implementation outside UCE-001.
