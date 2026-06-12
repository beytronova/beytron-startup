# PRD Writing Skill

Use when converting discovery into product requirements that can drive design, architecture, backlog, QA, and release planning.

## Triggers
- User asks for a PRD.
- Discovery has a continue recommendation.
- Backlog or architecture work needs product scope.

## Artifact Structure
Use `templates/PRD.template.md` and include:
- Status and approval
- Summary
- Problem
- Target users
- Goals
- Non-goals
- MVP scope
- User flows
- Acceptance criteria
- Metrics
- Dependencies
- Risks
- Open questions
- Handoff notes
- Readiness check

## Requirement Data Model
Acceptance criteria must be testable:

```text
Given ...
When ...
Then ...
```

Metrics must be measurable:

```text
Metric:
Definition:
Baseline:
Target:
Measurement method:
```

## Integration Standards
- Design work consumes PRD goals, user flows, and acceptance criteria.
- Architecture consumes MVP scope, constraints, data needs, integrations, and non-functional requirements.
- Jira backlog consumes acceptance criteria, dependencies, and release impact.
- QA consumes acceptance criteria and risks.

## Required Reading
- `roles/product.md`
- `workflows/discovery-to-prd.md`
- `templates/PRD.template.md`
- `governance/definition-of-ready.md`

## Protocol
1. Read discovery evidence, assumptions, risks, and approval state.
2. Define problem, target users, goals, non-goals, MVP scope, and user flows.
3. Write acceptance criteria in observable Given/When/Then or checklist form.
4. Define success metrics and product risks.
5. Keep implementation details out unless needed as constraints.
6. Prepare handoff notes for design and architecture.

## Output Format
- PRD using `templates/PRD.template.md`
- Product risks
- Open questions
- Handoff notes
- Readiness status

## Stop Conditions
- Discovery is missing.
- Target user is unclear.
- Acceptance criteria cannot be tested.
- Approval does not permit PRD work.

## Example Prompts
```text
Use PRD Writing to turn this discovery into a PRD with MVP scope, acceptance criteria, metrics, and handoff notes.
```
