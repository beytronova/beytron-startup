# Architecture Checklist

Use this checklist before moving from architecture to backlog or development.

## Required Inputs
- PRD
- Design brief when UI exists
- Platform constraints
- Existing codebase context when available
- Non-functional requirements
- Security/privacy assumptions

## Checklist
- [ ] Architecture traces to PRD acceptance criteria.
- [ ] System boundaries and components are clear.
- [ ] Data model and ownership are documented.
- [ ] API/contracts include input, output, validation, errors, and versioning.
- [ ] Integrations and dependencies are listed.
- [ ] Auth/authz rules are documented when relevant.
- [ ] Security/privacy implications are documented.
- [ ] Performance/reliability concerns are addressed.
- [ ] Observability needs are defined.
- [ ] Testability strategy is included.
- [ ] Migration and rollback impact are documented when relevant.
- [ ] Development handoff is possible.

## Pass Criteria
Architecture can move to backlog when developers can create small tickets without inventing boundaries, contracts, data ownership, or security assumptions.

## Block Conditions
- Core data model is unknown.
- API/data contract is missing.
- Security/privacy impact is unclear.
- Integration dependency is unknown.
- Target platform or repository is unclear.

## Missing Information Output
```text
Architecture is blocked because:
Missing technical decision:
Affected tickets/workflows:
Owner to resolve:
Recommended next step:
```
