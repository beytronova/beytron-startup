# GitHub Delivery Skill

Use when working with repositories, branches, pull requests, reviews, commits, repository setup, or release traceability.

## Triggers
- User asks to create or update repository files.
- Development work requires branches, commits, or pull requests.
- PR review, issue linking, or release traceability is needed.

## Repository Standards
- Read target repository `AGENTS.md` before changing files.
- Respect existing branch, commit, CI, PR, and review conventions.
- Keep work scoped to approved tickets.
- Preserve unrelated user changes.
- Do not perform destructive actions without explicit approval.

## Branch and Commit Standards
Recommended branch naming:

```text
feature/{ticket-key}-{short-slug}
fix/{ticket-key}-{short-slug}
docs/{ticket-key}-{short-slug}
```

Recommended commit shape:

```text
{ticket-key}: concise imperative summary
```

## Pull Request Standards
PR descriptions should include:
- Linked Jira ticket
- Linked PRD/architecture when relevant
- Summary
- Files/areas changed
- Tests/checks run
- Screenshots or evidence when UI exists
- Risks and rollback notes
- QA handoff

## Integration Standards
- Link Jira keys in branch, commit, PR title, and PR body when available.
- Keep release notes aligned with merged changes.
- Use GitHub checks as validation evidence.
- Do not create repositories unless approval and target ownership are explicit.

## Required Reading
- Target repository `AGENTS.md`
- `governance/approval-rules.md`
- `governance/coding-standards.md`
- `governance/release-gates.md` when release-related

## Protocol
1. Confirm target repository and permission level.
2. Read repository instructions before modifying files.
3. Verify approval state for repository creation, development, PR, or release actions.
4. Keep changes scoped to the approved ticket.
5. Link work to PRD, architecture, Jira issue, tests, and release notes where available.
6. Avoid destructive operations unless explicitly approved.
7. Verify repository actions before reporting success.

## Output Format
- Repository target
- Branch/PR/commit references when created
- Files changed
- Jira/PRD/architecture references
- Tests or checks
- Residual risk
- Next action

## Stop Conditions
- Target repo is unclear.
- Approval is missing.
- Repo instructions conflict with requested action.
- Destructive action lacks explicit approval.

## Example Prompts
```text
Use GitHub Delivery to update this repository, keep changes scoped to the approved ticket, and summarize verification.
```
