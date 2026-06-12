# Release Policy

This document defines how Beytron Startup versions, reviews, and releases plugin changes.

## Versioning Model

Beytron Startup uses semantic versioning.

```text
MAJOR.MINOR.PATCH
```

## Major Release

Use a major release when a change breaks existing behavior or requires users to change how they operate the plugin.

Examples:

- Approval model changes that alter when coding may start.
- Workflow order changes that remove, rename, or reorder required stages.
- Role contract changes that invalidate existing handoffs.
- Skill file format changes that existing agents cannot read.
- Plugin manifest changes that affect installation or compatibility.

Required before major release:

- Migration notes in `CHANGELOG.md`.
- Updated `README.md` usage instructions.
- Updated examples for changed workflows.
- Explicit owner approval.

## Minor Release

Use a minor release for new capabilities that do not break existing behavior.

Examples:

- New role.
- New skill.
- New workflow.
- New stack deep dive.
- New integration contract.
- New checklist.
- New template.
- New golden path example.

Required before minor release:

- `CHANGELOG.md` entry.
- Roadmap update when the change belongs to a planned phase.
- Registry update when routing, roles, skills, tools, or workflows are affected.
- Example update when the user-facing workflow changes.

## Patch Release

Use a patch release for safe documentation and wording improvements.

Examples:

- Typo fixes.
- Clarifying a rule without changing behavior.
- Formatting cleanup.
- Small template wording improvements.

Required before patch release:

- `CHANGELOG.md` entry when the change is user-visible.
- No broken links or references.

## Release Gates

Before declaring a release ready, verify:

- `.codex-plugin/plugin.json` version matches the intended release.
- `CHANGELOG.md` includes the release entry.
- `README.md` describes current capabilities.
- `AGENTS.md` has current operating rules.
- Routing registries reference existing files.
- New roles have matching skills or documented fallback behavior.
- New workflows have required inputs, outputs, approvals, and stop conditions.
- New checklists are referenced by workflows or `AGENTS.md` when they are required gates.
- New examples do not bypass approval, governance, or target repository instructions.

## Release Approval

A release may only be published when the owner explicitly approves it.

Required approval phrase:

```text
Approval Status = APPROVED_FOR_RELEASE
```

Without this approval, Codex may prepare release notes and update release artifacts, but must not publish tags, GitHub releases, packages, or marketplace submissions.

## Release Notes Format

Each release should include:

- Version
- Date
- Summary
- Added
- Changed
- Fixed
- Breaking changes, if any
- Migration notes, if any
- Verification performed
- Known risks

## Rollback

If a release introduces incorrect guidance or breaks plugin usage:

1. Stop further release actions.
2. Identify the last known good version.
3. Document the issue in `CHANGELOG.md` or a follow-up release note.
4. Revert or supersede the problematic files through a reviewed change.
5. Publish a patch release after owner approval.
