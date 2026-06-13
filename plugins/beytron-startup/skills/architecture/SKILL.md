---
name: architecture
description: Convert PRD and design scope into technical architecture, boundaries, API/data contracts, risks, dependencies, and development handoff.
---

# Architecture

Use this skill when product scope needs a technical plan before Jira tickets or development.

## Purpose

Architecture defines how the product will be built without prematurely writing product code.

## Required Inputs

- PRD.
- Design brief or UX flow when applicable.
- Current approval status.
- Target platform and repository context.
- Security, data, integration, and release constraints.

## Outputs

- System architecture.
- Module boundaries.
- API contracts.
- Data model and migration notes.
- Auth and permission model.
- Observability and logging plan.
- Security and privacy risks.
- Development handoff.

## Rules

- Prefer existing repo patterns and stack decisions.
- Mark unknowns and alternatives.
- Do not create product code.
- Do not start development without approved tickets and `APPROVED_FOR_DEVELOPMENT`.

## Quality Bar

Architecture is ready for backlog only when engineers can estimate, QA can plan tests, and security risks are visible.
