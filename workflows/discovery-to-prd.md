# Discovery to PRD

## Purpose
Convert validated discovery into a product requirements document that can drive design, architecture, backlog, QA, release, and growth.

## Trigger
Discovery has a continue recommendation and the user asks for PRD or product scope.

## Required Approval
- Minimum: `APPROVED_FOR_DESIGN` or explicit user request to draft PRD.
- If approval is unclear, draft may be created but must be marked pending approval.

## Required Roles
- Product
- Product Designer for user flow support
- Data Analytics for metrics
- QA Developer for testable acceptance criteria

## Required Inputs
- Discovery summary
- Problem statement
- Target users
- Evidence and assumptions
- Business constraints
- Approval status

## Steps
1. Read discovery and open questions.
2. Define problem, users, goals, non-goals, MVP, flows, acceptance criteria, metrics, and risks.
3. Keep acceptance criteria observable and testable.
4. Identify design, architecture, analytics, QA, and release implications.
5. Prepare product-to-design and product-to-architecture handoff notes.

## Outputs
- PRD
- Product risks
- Open questions
- Handoff inputs
- Readiness status

## Artifact Target
- PRD artifact in project docs or active idea workspace.

## Tool Usage
- Do not create code.
- Do not create Jira issues until backlog workflow.

## Failure Handling
- If MVP scope is too broad, split must-have from later scope.
- If success cannot be measured, block with analytics questions.
- If acceptance criteria are not testable, revise before moving forward.
