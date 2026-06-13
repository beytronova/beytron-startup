---
name: github-delivery
description: Plan and execute GitHub delivery with repository context, AGENTS rules, branches, commits, pull requests, reviews, CI, and release-safe changes.
---

# GitHub Delivery

Use this skill when approved work needs repository inspection, branch planning, implementation sequencing, PR creation, CI review, or code review handling.

## Required Inputs

- Target repository.
- Jira ticket or approved scope.
- PRD and architecture references.
- Current approval status.
- Repository `AGENTS.md`.

## Rules

- Read target repo instructions before code changes.
- Keep changes scoped to ticket acceptance criteria.
- Do not overwrite unrelated user changes.
- Use tests and CI evidence.
- Create PRs only when permitted.

## Outputs

- Branch plan.
- Implementation plan.
- Commit/PR summary.
- Test evidence.
- Review response plan.

## Stop Conditions

- Missing target repository.
- Missing approval for development.
- Missing or conflicting repo instructions.
