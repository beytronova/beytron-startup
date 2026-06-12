# UX Product Design Skill

Use when translating PRD scope into user flows, screen inventory, interaction states, and design handoff notes.

## Triggers
- User asks for UX, UI, wireframe, design brief, or user flow work.
- PRD is approved for design.
- Developers need screen and state clarity before implementation.

## Artifact Structure
Use `templates/DESIGN_BRIEF.template.md` and include:
- Product context
- Target users
- Primary user flows
- Screen inventory
- Interaction states
- Accessibility notes
- UX risks
- Open questions
- Handoff checklist

## Design Data Model
Screen inventory should follow:

```text
Screen:
Purpose:
Entry points:
Primary action:
Secondary actions:
States: Loading / Empty / Error / Success / Permission / Offline
Analytics events:
Accessibility notes:
```

## Implementation Handoff Standards
- Name screens and states consistently.
- Include edge cases and validation messages.
- Include responsive/platform notes for web/mobile.
- Include accessibility and localization considerations.
- Flag design choices that affect architecture or data model.

## Required Reading
- `roles/product-designer.md`
- `workflows/prd-to-design.md`
- `templates/DESIGN_BRIEF.template.md`
- `handoffs/product-to-design.md`

## Protocol
1. Read PRD goals, user flows, acceptance criteria, and constraints.
2. Identify primary, secondary, and failure flows.
3. Produce screen inventory and interaction state matrix.
4. Include loading, empty, error, success, permission, offline, and onboarding states where relevant.
5. Note accessibility, responsive, localization, and platform constraints.
6. Prepare design handoff to architecture and development.

## Output Format
- Design brief
- Flow list
- Screen inventory
- State matrix
- UX risks
- Open questions

## Stop Conditions
- PRD is missing or unstable.
- User flow is unclear.
- Platform target is unknown.

## Example Prompts
```text
Use UX Product Design to create a design brief, user flows, screen inventory, and state matrix from this PRD.
```
