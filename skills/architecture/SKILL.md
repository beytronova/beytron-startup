# Architecture Skill

Use when converting PRD, design context, platform constraints, and non-functional requirements into implementation-ready architecture.

## Triggers
- User asks for architecture, system design, technical design, API/data contracts, or implementation plan.
- Workflow reaches `prd-to-architecture`.
- Backlog or development is blocked by unclear modules, data model, integrations, security, or testability.

## Supported Architecture Domains
- Web applications and BFFs
- Backend services and APIs
- Flutter, iOS, and Android applications
- Event-driven systems, jobs, queues, and integrations
- Data models, persistence, migrations, and analytics event contracts
- Security, privacy, observability, reliability, and release constraints

## Required Inputs
- PRD
- Design brief when UI exists
- Acceptance criteria
- Platform and target repository constraints
- Existing codebase context when available
- Non-functional requirements
- Approval status

## Required Reading
- `roles/architect.md`
- `workflows/prd-to-architecture.md`
- `templates/ARCHITECTURE.template.md`
- `handoffs/product-to-architecture.md`
- `handoffs/architecture-to-development.md`
- `governance/coding-standards.md`
- `governance/security-standards.md`
- `governance/definition-of-ready.md`

## Protocol
1. Verify approval, PRD scope, acceptance criteria, design context, and target platform.
2. Identify system boundaries, modules, data ownership, integration points, and runtime environments.
3. Define API/data contracts, validation rules, error behavior, and migration impact.
4. Document security, privacy, observability, reliability, performance, and testability concerns.
5. Decide implementation sequence and development handoff requirements.
6. Flag decisions that must be made before backlog or development.

## Architecture Decision Model
Use this format for each important decision:

```text
Decision:
Context:
Options considered:
Chosen option:
Why:
Tradeoffs:
Risks:
Owner:
Review trigger:
```

## Contract Model
Use explicit contracts:

```text
Contract name:
Producer:
Consumer:
Input:
Output:
Validation:
Errors:
Versioning:
Security/privacy notes:
Test strategy:
```

## Output Format
- Architecture overview
- Components and boundaries
- Data model
- API/contracts
- Integrations
- Security/privacy notes
- Performance/reliability notes
- Testability strategy
- Risks and tradeoffs
- Development handoff
- Open questions

## Quality Gates
- Architecture traces back to PRD acceptance criteria.
- Data/API contracts are explicit enough for ticket creation.
- Security/privacy concerns are documented.
- Testability and observability are addressed.
- Development can begin without inventing system boundaries.

## Stop Conditions
- PRD scope is unclear.
- Core data model is unknown.
- Auth/security/privacy impact is unresolved.
- Integration dependency is unknown.
- Target platform or repository is unclear.

## Example Prompts
```text
Use Architecture to turn this PRD and design brief into an implementation-ready architecture with contracts, risks, and development handoff.
```
