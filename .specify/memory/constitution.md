<!--
Sync Impact Report
- Version change: N/A → 1.0.0
- Modified principles: placeholders → concrete names and rules
- Added sections: Additional Constraints (Training Context); Development Workflow & Quality Gates
- Removed sections: None
- Templates requiring updates:
	✅ .specify/templates/plan-template.md (Constitution Check gates)
	✅ .specify/templates/spec-template.md (security requirements note)
	⚠ pending: .specify/templates/commands/ (directory missing; create and align command docs if adopted)
- Deferred TODOs: TODO(RATIFICATION_DATE) — original adoption date not recorded; please provide
-->

# ContosoDashboard Constitution

## Core Principles

### I. Spec-Driven Development (NON-NEGOTIABLE)
All feature work MUST begin with a written specification using the
repository templates under `.specify/templates/`. A valid spec includes
prioritized user stories, independent tests or manual acceptance scenarios,
and measurable success criteria. No code MAY be merged without a linked
spec, a generated plan (`/speckit.plan`), and tasks (`/speckit.tasks`).

**Rationale**: Ensures clarity, traceability, and incremental delivery in
this training environment.

### II. Test Discipline: Red-Green-Refactor When Tests Are Requested
When a spec requests tests, they MUST be written first, verified failing,
then implemented to pass, followed by refactor. If a spec opts for manual
acceptance only, acceptance scenarios MUST be executable via application
pages and reviewed before merge.

**Rationale**: Preserves learning focus while enforcing high-signal test
cycles where requested.

### III. Security & Authorization by Design
Authorization MUST be enforced at the page and service layers to prevent
IDOR and unauthorized access. Role checks MUST gate sensitive operations.
Security headers and defense-in-depth SHOULD be maintained consistent with
training constraints. Mock authentication MAY be used only for training; do
not treat it as production-ready.

**Rationale**: Security posture is a core learning objective; guardrails
must be explicit.

### IV. Offline‑First Infrastructure Abstraction
Infrastructure dependencies (storage, auth, database, file handling) MUST be
abstracted behind interfaces and selected via dependency injection.
Business logic MUST NOT directly depend on cloud SDKs. Implementations MAY
be swapped (e.g., Local → Azure) via configuration without changing business
code.

**Rationale**: Supports offline training and a clear migration path to cloud
providers.

### V. Simplicity & Transparency
Favor minimal dependencies, clear separation of concerns, and straightforward
flows. Logging SHOULD be structured enough to diagnose issues locally.
Versioning MUST follow semantic versioning for governance documents and any
public interfaces exposed in training exercises.

**Rationale**: Simplicity accelerates learning and reduces incidental
complexity.

## Additional Constraints (Training Context)

This repository is for training only and MUST NOT be deployed to
production. External services SHOULD NOT be introduced unless the spec
explicitly requires them for a migration exercise. No real credentials or
personally identifiable data MAY be used. Where cloud migration is taught,
use abstractions and configuration-only swaps.

## Development Workflow & Quality Gates

- Spec-first: Each PR MUST reference a spec and plan.
- Constitution Check: Plans MUST document gates derived from this
	constitution (spec completeness, security enforcement strategy,
	abstraction points, simplicity review).
- Code review: Reviewers MUST verify adherence to principles and acceptance
	scenarios/tests.
- Task organization: `/speckit.tasks` output MUST group tasks by user story
	to preserve independent delivery.
- Versioning: Governance changes MUST bump the constitution version per
	semantic rules and include a Sync Impact Report.

## Governance

The Constitution supersedes other practices in this training repository.
Amendments MUST be proposed via PR with:
- Summary of changes and compatibility impact
- Updated Constitution version per semantic rules
- Migration/adjustment notes for templates or workflows
- Re-run of Constitution Check in the affected plan(s)

Compliance reviews MUST confirm that specs, plans, and tasks align with the
Core Principles and Quality Gates before merge.

**Version**: 1.0.0 | **Ratified**: TODO(RATIFICATION_DATE): original adoption date not recorded | **Last Amended**: 2026-01-13

# [PROJECT_NAME] Constitution
<!-- Example: Spec Constitution, TaskFlow Constitution, etc. -->

## Core Principles

### [PRINCIPLE_1_NAME]
<!-- Example: I. Library-First -->
[PRINCIPLE_1_DESCRIPTION]
<!-- Example: Every feature starts as a standalone library; Libraries must be self-contained, independently testable, documented; Clear purpose required - no organizational-only libraries -->

### [PRINCIPLE_2_NAME]
<!-- Example: II. CLI Interface -->
[PRINCIPLE_2_DESCRIPTION]
<!-- Example: Every library exposes functionality via CLI; Text in/out protocol: stdin/args → stdout, errors → stderr; Support JSON + human-readable formats -->

### [PRINCIPLE_3_NAME]
<!-- Example: III. Test-First (NON-NEGOTIABLE) -->
[PRINCIPLE_3_DESCRIPTION]
<!-- Example: TDD mandatory: Tests written → User approved → Tests fail → Then implement; Red-Green-Refactor cycle strictly enforced -->

### [PRINCIPLE_4_NAME]
<!-- Example: IV. Integration Testing -->
[PRINCIPLE_4_DESCRIPTION]
<!-- Example: Focus areas requiring integration tests: New library contract tests, Contract changes, Inter-service communication, Shared schemas -->

### [PRINCIPLE_5_NAME]
<!-- Example: V. Observability, VI. Versioning & Breaking Changes, VII. Simplicity -->
[PRINCIPLE_5_DESCRIPTION]
<!-- Example: Text I/O ensures debuggability; Structured logging required; Or: MAJOR.MINOR.BUILD format; Or: Start simple, YAGNI principles -->

## [SECTION_2_NAME]
<!-- Example: Additional Constraints, Security Requirements, Performance Standards, etc. -->

[SECTION_2_CONTENT]
<!-- Example: Technology stack requirements, compliance standards, deployment policies, etc. -->

## [SECTION_3_NAME]
<!-- Example: Development Workflow, Review Process, Quality Gates, etc. -->

[SECTION_3_CONTENT]
<!-- Example: Code review requirements, testing gates, deployment approval process, etc. -->

## Governance
<!-- Example: Constitution supersedes all other practices; Amendments require documentation, approval, migration plan -->

[GOVERNANCE_RULES]
<!-- Example: All PRs/reviews must verify compliance; Complexity must be justified; Use [GUIDANCE_FILE] for runtime development guidance -->

**Version**: [CONSTITUTION_VERSION] | **Ratified**: [RATIFICATION_DATE] | **Last Amended**: [LAST_AMENDED_DATE]
<!-- Example: Version: 2.1.1 | Ratified: 2025-06-13 | Last Amended: 2025-07-16 -->
