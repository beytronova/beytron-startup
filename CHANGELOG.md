# Changelog

All notable changes to Beytron Startup are documented in this file.

This project follows semantic versioning for plugin-level changes:

- Major: breaking changes to routing, role contracts, workflow order, approval gates, or plugin manifest compatibility.
- Minor: new roles, skills, workflows, integrations, checklists, examples, or governance files.
- Patch: clarifications, typo fixes, non-breaking documentation improvements, or small template refinements.

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
