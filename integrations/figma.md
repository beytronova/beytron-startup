# Figma Integration

## Purpose
Use Figma to read design context, generate design artifacts, inspect product screens, create editable design files, and connect design decisions to implementation handoffs.

## Required Access
- Read access to relevant Figma files for design-to-code or design review work.
- Write access only when creating or updating Figma files is explicitly requested.
- Access to team/project information when creating new files.

## Authentication
Figma access must come from an authorized Figma connector or app.

Before write operations, verify:

- Target Figma file or project
- Design scope
- Role and workflow
- Approval or explicit user request

## Inputs
- PRD
- Design brief
- Existing Figma link when available
- Target platform
- Screen or component scope
- Brand/design system constraints
- Approval status

## Outputs
- Figma file or frame link
- Design context summary
- Screen/component inventory
- Interaction state notes
- Accessibility notes
- Design-to-development handoff

## Workflow Usage

Allowed workflows:

- `workflows/prd-to-design.md`
- `workflows/prd-to-architecture.md` when design affects system constraints
- `workflows/backlog-to-development.md` when implementation needs design context

Write operations are allowed only with explicit user request.

## Design Handoff Standards
A Figma-derived handoff should include:

- Target screens/components
- States: loading, empty, error, success, permission, offline
- Responsive/platform variants
- Tokens/components used
- Accessibility considerations
- Open design questions

## Failure Handling
- If Figma access is missing, continue with text-based design brief and record limitation.
- If design conflicts with PRD, route back to Product/Product Designer.
- If design lacks required states, request or define missing states before development.
- If Figma write fails, provide the intended design artifact as markdown and report the failure.
