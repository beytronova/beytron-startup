# Repo Bootstrap Checklist

Use this checklist before creating a new product repository.

## Required Inputs

- Approved idea slug
- Product repository name
- Repository owner
- Visibility
- PRD
- Architecture
- Ticket drafts
- Approval artifact
- Intended stack
- Initial maintainers

## Pass Criteria

- Approval status is `APPROVED_FOR_REPO_CREATION`.
- Product name and repository name are clear.
- Repository owner and visibility are explicit.
- Source artifacts are linked or copied.
- PRD and architecture are approved enough for repository creation.
- Initial repository files are defined.
- Target stack is documented.
- Security and data assumptions are documented.
- No product development is being started yet.
- Next approval for development is identified.

## Block Conditions

Block repository creation if:

- Approval status is missing or not `APPROVED_FOR_REPO_CREATION`.
- PRD or architecture is missing.
- Repository ownership is unclear.
- Visibility is unclear.
- Security/data handling assumptions are unknown.
- User asks to start development before `APPROVED_FOR_DEVELOPMENT`.
- The request includes unrelated products or open-source repositories not approved in this flow.

## Output Format

```text
Repo bootstrap checklist: PASS|BLOCKED
Approval: {status}
Repository: {owner/name}
Source artifacts: {ready|missing}
Security notes: {ready|missing}
Development approval: {needed|already approved}
Blockers: {list}
Next step: {specific action}
```
