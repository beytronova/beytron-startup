# Product to Architecture Handoff

## Purpose
Transfer product scope into technical architecture planning with clear boundaries and constraints.

## Source Role
Product

## Receiver Role
Architect

## Required Source Artifacts
- PRD
- MVP scope
- Non-goals
- Acceptance criteria
- Metrics
- Design brief if available
- Business and platform constraints
- Product risks

## Handoff Checklist
- [ ] PRD link or artifact path is included.
- [ ] MVP scope and non-goals are explicit.
- [ ] Acceptance criteria are testable.
- [ ] Data, integration, and platform needs are listed.
- [ ] Non-functional needs are stated or marked unknown.
- [ ] Security/privacy assumptions are listed.
- [ ] Approval state is included.

## Receiver Outputs
- Architecture
- Component model
- Data/API contracts
- Technical risks
- Development handoff

## Acceptance Conditions
The handoff is accepted when the Architect can define system boundaries and implementation constraints without inventing product scope.

## Blocker Format
```text
Blocked because:
Needed from Product:
Technical impact if unresolved:
Recommended next step:
```

## Stop Conditions
- Scope is unstable.
- Key product decisions are unresolved.
- Non-functional needs are missing.
- Security/privacy assumptions are unclear.
