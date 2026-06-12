# Approval Rules

## Required Approval States

- `WAITING`
- `APPROVED_FOR_DISCOVERY`
- `APPROVED_FOR_DESIGN`
- `APPROVED_FOR_ARCHITECTURE`
- `APPROVED_FOR_BACKLOG`
- `APPROVED_FOR_DEVELOPMENT`
- `APPROVED_FOR_RELEASE`
- `REJECTED`

## Rules

- No code before `APPROVED_FOR_DEVELOPMENT`.
- No release before `APPROVED_FOR_RELEASE`.
- Approval must reference PRD, architecture, ticket scope, tests, risks, and owner.
