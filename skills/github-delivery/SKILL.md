# GitHub Delivery Skill

Use when working with repositories, branches, pull requests, reviews, commits, repository setup, or release traceability.

## Triggers
- User asks to create or update repository files.
- Development work requires branches, commits, or pull requests.
- PR review, issue linking, or release traceability is needed.

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
- Files changed
- Jira/PRD/architecture references
- Tests or checks
- Residual risk
- Next action

## Quality Gates
- Repo instructions were respected.
- Changes are traceable.
- No unrelated files were changed.
- Verification result is stated.

## Stop Conditions
- Target repo is unclear.
- Approval is missing.
- Repo instructions conflict with requested action.
- Destructive action lacks explicit approval.

## Example Prompts
```text
Use GitHub Delivery to update this repository, keep changes scoped to the approved ticket, and summarize verification.
```
