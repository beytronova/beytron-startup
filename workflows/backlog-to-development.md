# Backlog to Development

## Purpose
Start implementation only for approved, ready, scoped tickets in the target product repository.

## Trigger
A backlog item is ready and user approves development.

## Required Approval
- Required: `APPROVED_FOR_DEVELOPMENT`

## Required Roles
- Relevant developer role
- Architect when technical ambiguity exists
- QA Developer for test impact
- Security Reviewer for sensitive scope

## Required Inputs
- Jira issue or approved ticket draft
- PRD
- Architecture
- Design brief when UI exists
- Approval status
- Target product repository
- Repository `AGENTS.md`

## Steps
1. Verify approval and Definition of Ready.
2. Read target repository instructions.
3. Read PRD, architecture, design, and ticket scope.
4. Implement only approved scope.
5. Run relevant checks or document blockers.
6. Produce implementation summary and development-to-QA handoff.

## Outputs
- Code changes in product repo
- Tests or validation notes
- Implementation summary
- QA handoff

## Artifact Target
- Product repository code and implementation notes.

## Tool Usage
- GitHub tools may be used for repository reads/writes, branches, commits, or PRs when requested.
- Do not create new product repositories in this workflow.

## Failure Handling
- If approval is missing, stop.
- If repository is missing, route to repository creation workflow outside this plugin.
- If architecture or design is unresolved, route back before coding.
- If tests cannot be identified, request QA input.
