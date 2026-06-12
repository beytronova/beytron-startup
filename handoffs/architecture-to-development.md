# Architecture to Development Handoff

## Purpose
Transfer technical design into implementation-ready development work.

## Source Role
Architect

## Receiver Role
Relevant developer role

## Required Source Artifacts
- Architecture
- PRD
- Design brief when UI exists
- Jira issue or approved ticket scope
- API/data contracts
- Dependency map
- Risks and mitigations
- Approval state
- Target repository

## Handoff Checklist
- [ ] Target repository is identified.
- [ ] Ticket scope is approved and linked.
- [ ] Architecture artifact is linked.
- [ ] API/data contracts are explicit.
- [ ] Security/privacy notes are included.
- [ ] Test impact is described.
- [ ] Release or migration impact is described.
- [ ] Definition of Ready passes.

## Receiver Outputs
- Implementation plan
- Code changes after approval
- Tests or validation notes
- Development-to-QA handoff

## Acceptance Conditions
The handoff is accepted when the developer can implement the ticket without guessing architecture, data contracts, security constraints, or approval status.

## Blocker Format
```text
Blocked because:
Needed from Architect/Product:
Development impact if unresolved:
Recommended next step:
```

## Stop Conditions
- Interface contract is unclear.
- Approval is missing.
- Ticket scope is not ready.
- Security risk is unresolved.
- Target repository is missing.
