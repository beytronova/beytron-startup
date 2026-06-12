# GitHub Execution Playbook

Use this playbook when Codex needs to inspect repositories, create branches, modify files, open pull requests, or prepare release-related GitHub work.

## Required Reads

- `config/tool-access.yaml`
- `integrations/github.md`
- Target repository `AGENTS.md`
- Relevant workflow under `workflows/`
- Relevant role and skill files
- `governance/coding-standards.md`
- `governance/testing-standards.md`

## Allowed Actions by Approval

### No Approval

Allowed:

- Inspect public repository metadata and files when access exists.
- Explain proposed branch, PR, or repository changes.
- Draft file changes conceptually.

Not allowed:

- Create branches.
- Commit changes.
- Open PRs.
- Create repositories.
- Delete files or repositories.

### APPROVED_FOR_REPO_CREATION

Allowed:

- Propose product repository creation from repo bootstrap templates.
- Create the repository only if the user explicitly asks for execution and tool access permits it.

Required:

- Approved idea
- Product name
- Repository owner
- Repository visibility
- Bootstrap checklist pass

### APPROVED_FOR_DEVELOPMENT

Allowed:

- Create or use a feature branch.
- Implement approved ticket scope.
- Commit changes.
- Open draft PR when requested or workflow permits it.

Required:

- Ticket reference
- Target repository
- PRD and architecture references
- Test plan
- Target repo `AGENTS.md` read

### APPROVED_FOR_RELEASE

Allowed:

- Create release tags or GitHub releases only when release workflow explicitly permits publishing.

## Branch Naming

Recommended format:

```text
{ticket-id}-{short-slug}
```

Examples:

```text
BEY-12-subscription-prediction
BEY-31-prediction-api
```

If no ticket exists, do not create a development branch unless the workflow explicitly permits non-ticket work.

## Pull Request Standard

PR body should include:

- Linked Jira ticket(s)
- Summary
- Scope
- Out of scope
- PRD reference
- Architecture reference
- Test evidence
- Screenshots or recordings for UI changes
- Security/privacy notes
- Rollback notes
- Checklist status

## Repository Inspection Sequence

1. Read target repository `AGENTS.md`.
2. Identify stack and package/build tooling.
3. Read relevant plugin role, skill, stack deep dive, and workflow.
4. Inspect affected files and tests.
5. Identify smallest safe implementation path.
6. Confirm test commands.

## Implementation Sequence

1. Confirm approval and ticket scope.
2. Create or select branch.
3. Make scoped changes.
4. Add or update tests.
5. Run targeted verification.
6. Prepare QA handoff.
7. Open draft PR when approved.
8. Link PR to Jira when approved.

## Failure Handling

If GitHub access is unavailable:

- Produce a local implementation plan or patch proposal.
- State that no repository changes were made.
- List required access and next action.

If tests cannot run:

- Explain why.
- Provide the exact commands attempted or recommended.
- Mark verification as incomplete.

If target repo instructions conflict with plugin guidance:

- Target repository `AGENTS.md` wins for code-level work.
- Record the conflict in the final response.

## Final Response Format

```text
GitHub action: {inspect|branch|commit|PR|release}
Approval: {status}
Repository: {owner/repo}
Branch: {branch or none}
Tickets: {keys}
Changes: {summary}
Verification: {commands and results}
PR: {url or not created}
Blockers: {if any}
Next step: {specific action}
```
