# PRD to Architecture

## Purpose
Convert PRD and design context into technical architecture, contracts, risks, and implementation constraints.

## Trigger
A PRD exists and technical planning is needed before backlog or development.

## Required Approval
- Minimum: `APPROVED_FOR_ARCHITECTURE`

## Required Roles
- Architect
- Backend Developer when APIs/data are involved
- Mobile Lead or Web Developer depending on platform
- Security Reviewer for sensitive data
- QA Developer for testability

## Required Inputs
- PRD
- Design brief when UI exists
- Platform constraints
- Existing codebase context if available
- Non-functional requirements
- Approval status

## Steps
1. Read PRD, design brief, constraints, and target platform.
2. Define modules, data flow, data ownership, integrations, and contracts.
3. Document API/data contracts and dependency boundaries.
4. Identify security, privacy, reliability, observability, performance, and testability risks.
5. Produce development handoff.

## Outputs
- Architecture
- Data/API contracts
- Technical risks and mitigations
- Development handoff

## Artifact Target
- Architecture artifact in project docs or active idea workspace.

## Tool Usage
- Do not create code.
- Do not create repository structure unless repository creation is explicitly approved.

## Failure Handling
- If core data model is unknown, block backlog creation.
- If sensitive data risk is unclear, route to Security Reviewer.
- If platform target is unclear, route to Product or Mobile Lead.
