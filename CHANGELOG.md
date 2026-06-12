# Changelog

All notable changes to Beytron Startup are documented in this file.

This project follows semantic versioning for plugin-level changes:

- Major: breaking changes to routing, role contracts, workflow order, approval gates, or plugin manifest compatibility.
- Minor: new roles, skills, workflows, integrations, checklists, examples, or governance files.
- Patch: clarifications, typo fixes, non-breaking documentation improvements, or small template refinements.

## [0.4.3] - Android Development Hardening

### Added

- Android XML Views stack deep dive: `skills/android-development/stacks/xml-views.md`.
- Android Coroutines and Flow deep dive: `skills/android-development/stacks/coroutines-flow.md`.
- Android Room and DataStore deep dive: `skills/android-development/stacks/room-datastore.md`.
- Android Networking deep dive: `skills/android-development/stacks/networking.md`.
- Android Hilt dependency injection deep dive: `skills/android-development/stacks/hilt.md`.
- Android testing guide: `skills/android-development/guides/testing.md`.
- Android performance guide: `skills/android-development/guides/performance.md`.
- Android flavors and release guide: `skills/android-development/guides/flavors-release.md`.
- Android accessibility and i18n guide: `skills/android-development/guides/accessibility-i18n.md`.

### Changed

- `skills/android-development/SKILL.md` now references the new Android stack deep dives and production guides.
- `skills/android-development/stacks/README.md` now indexes Android stack and companion guide selection rules.
- Plugin manifest version updated to `0.4.3`.

### Operational Notes

- Android work now has stronger guidance for XML Views, Compose, coroutines/Flow, Room/DataStore, networking, Hilt, testing, performance, release variants, accessibility, localization, and mobile privacy.

## [0.4.2] - Flutter Development Hardening

### Added

- Flutter BLoC stack deep dive: `skills/flutter-development/stacks/bloc.md`.
- Flutter Provider stack deep dive: `skills/flutter-development/stacks/provider.md`.
- Flutter Firebase stack deep dive: `skills/flutter-development/stacks/firebase.md`.
- Flutter platform channels deep dive: `skills/flutter-development/stacks/platform-channels.md`.
- Flutter performance guide: `skills/flutter-development/guides/performance.md`.
- Flutter testing guide: `skills/flutter-development/guides/testing.md`.
- Flutter flavors and release guide: `skills/flutter-development/guides/flavors-release.md`.
- Flutter accessibility and i18n guide: `skills/flutter-development/guides/accessibility-i18n.md`.

### Changed

- `skills/flutter-development/SKILL.md` now references the new stack deep dives and production guides.
- `skills/flutter-development/stacks/README.md` now indexes Flutter stack and companion guide selection rules.
- Plugin manifest version updated to `0.4.2`.

### Operational Notes

- Flutter work now has stronger guidance for state management, Firebase, native platform channels, performance, testing, release flavors, accessibility, localization, and mobile privacy.

## [0.4.1] - Centralized Approval Statuses and Role Creation Rules

### Added

- Canonical approval status policy: `governance/approval-statuses.md`.
- Machine-readable approval status registry: `config/approval-statuses.yaml`.
- Role creation rules: `governance/role-creation-rules.md`.
- Role template: `templates/ROLE.template.md`.
- Role creation checklist: `checklists/role-creation-checklist.md`.

### Changed

- `AGENTS.md` now requires approval validation before workflow routing and role creation validation before completing new roles.
- `README.md` now documents the approval layer, centralized source of truth, and role creation layer.
- `USAGE.md` now requires only canonical approval statuses and includes approval-aware final response format.
- `CONTRIBUTING.md` now routes role additions through the role creation rules, role template, and role creation checklist.
- Plugin manifest version updated to `0.4.1`.

### Operational Notes

- Unknown approval statuses are blockers.
- If any file conflicts with centralized approval definitions, `governance/approval-statuses.md` and `config/approval-statuses.yaml` win.
- New roles must create/update required role, skill, registry, workflow, handoff, checklist, example, validation, and changelog artifacts as applicable.

## [0.4.0] - Usage, Execution, Bootstrap, Validation, and Security Hardening

### Added

- Installation and usage guides with practical invocation prompts: `INSTALL.md`, `USAGE.md`.
- Jira and GitHub execution playbooks: `playbooks/jira-execution.md`, `playbooks/github-execution.md`, `playbooks/jira-github-delivery.md`.
- Product repository bootstrap flow with proposal template and checklist.
- Prompt-based validation test scenarios for idea-to-PRD, Jira-to-development, repo bootstrap, release approval, and security review.
- Security hardening guides for data classification, secret handling, threat modeling, compliance, and mobile privacy.
- v0.4 roadmap documenting Phases 8 through 12.

### Changed

- Plugin manifest version updated to `0.4.0`.
- README now documents operation layers for installation, playbooks, bootstrap, validation, and security hardening.
- AGENTS now requires installation/usage guidance, execution playbooks, validation scenarios, and security hardening files where relevant.

### Operational Notes

- Jira and GitHub side effects remain gated by explicit approval and `config/tool-access.yaml`.
- Product repository creation is gated by `APPROVED_FOR_REPO_CREATION`.
- Development remains gated by `APPROVED_FOR_DEVELOPMENT`.
- Release publishing remains gated by `APPROVED_FOR_RELEASE`.
- Sensitive data uncertainty is treated as a blocker.

## [0.3.0] - Routing, Governance, and Golden Paths

### Added

- Routing registry foundation with `config/workflow-map.yaml`, `config/role-skill-map.yaml`, and `config/tool-access.yaml`.
- Core skills for architecture, data analytics, and security review.
- Integration contracts for GitHub, Jira, web search, Figma, and release systems.
- Validation checklists for discovery, PRD, design, architecture, ticket readiness, development handoff, QA, and release.
- Stack deep dives for Next.js, React Vite, NestJS, FastAPI, Flutter Riverpod, Android Jetpack Compose, and iOS SwiftUI.
- Golden path examples for idea-to-release, Jira-ticket-to-PR, mobile feature delivery, backend API delivery, and growth experiments.
- Release discipline documents: `CHANGELOG.md`, `RELEASE_POLICY.md`, and `CONTRIBUTING.md`.

### Changed

- `README.md` now documents routing, validation, example, and release discipline layers.
- `AGENTS.md` now requires registry routing, checklist validation, governance review, and release discipline for substantive changes.

### Operational Notes

- Development remains blocked unless approval, ticket scope, PRD, architecture, target repository, and test impact are clear.
- Tool side effects such as Jira creation, GitHub branches, pull requests, repository creation, and releases still require explicit approval or workflow permission.

## [0.2.0] - Role and Skill Expansion

### Added

- Expanded agile delivery roles for product, design, architecture, web, backend, mobile, QA, automation, release, growth, analytics, and security.
- Expanded skills for platform-specific implementation and delivery responsibilities.
- Initial handoffs, templates, and governance documents.

## [0.1.0] - Initial Plugin Skeleton

### Added

- Initial Codex plugin manifest.
- Base `README.md` and `AGENTS.md`.
- Initial `roles/`, `skills/`, `workflows/`, `handoffs/`, `templates/`, and `governance/` structure.
