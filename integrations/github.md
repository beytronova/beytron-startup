# GitHub Integration

## Purpose
Use GitHub to read repositories, update approved files, create branches or pull requests, inspect PRs/issues, and preserve traceability between product artifacts, Jira tickets, code changes, tests, and releases.

## Required Access
- Repository read access for inspection and context gathering.
- Repository contents write access for approved documentation or code changes.
- Pull request access for creating or reviewing PRs.
- Issues access when GitHub Issues are used for project tracking.
- Actions/checks read access for CI validation.

## Authentication
GitHub access must come from an authorized GitHub App, connector, or approved local Git remote credential.

Before write operations, verify:

- Target repository
- Permission level
- Default branch
- Repository `AGENTS.md`
- Requested scope
- Approval state

## Inputs
- Target repository
- Branch or default branch context
- Jira issue key or approved ticket draft when development is involved
- PRD, architecture, design, or release artifact references
- Files to read or update
- Approval status

## Outputs
- Files read or changed
- Commit SHA when changes are committed
- Branch name when created
- Pull request link when created
- CI/check status when available
- Verification summary
- Residual risk and next action

## Workflow Usage

### Allowed Read Workflows
- `workflows/backlog-to-development.md`
- `workflows/development-to-qa.md`
- `workflows/qa-to-release.md`
- Any workflow requiring repository context, when read-only access is sufficient

### Allowed Write Workflows
- `workflows/backlog-to-development.md` after `APPROVED_FOR_DEVELOPMENT`
- `workflows/development-to-qa.md` when adding approved tests or QA docs
- `workflows/qa-to-release.md` after `APPROVED_FOR_RELEASE` for release notes/tags only when requested

## Write Rules
- Do not write before reading repository instructions.
- Do not change files outside approved scope.
- Do not create branches, commits, PRs, tags, releases, or repositories unless explicitly requested or permitted by workflow approval.
- Do not perform destructive actions without explicit user approval.
- Preserve unrelated user changes.

## Branch and PR Standards
Recommended branch names:

```text
feature/{ticket-key}-{short-slug}
fix/{ticket-key}-{short-slug}
docs/{ticket-key}-{short-slug}
```

PR descriptions should include:

- Linked Jira ticket
- PRD/architecture references
- Summary
- Files/areas changed
- Tests/checks run
- Risks and rollback notes
- QA handoff

## Failure Handling
- If repository is missing, stop and request target repository.
- If write access is missing, report permission status and do not attempt bypasses.
- If `AGENTS.md` conflicts with the requested change, stop and report the conflict.
- If CI/checks fail, route to QA or fix workflow depending on scope.
- If destructive action is requested ambiguously, ask for explicit confirmation.
