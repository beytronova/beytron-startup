# Approval Rules

## Required Approval States

- `WAITING`
- `APPROVED_FOR_DISCOVERY`
- `APPROVED_FOR_DESIGN`
- `APPROVED_FOR_ARCHITECTURE`
- `APPROVED_FOR_BACKLOG`
- `APPROVED_FOR_DEVELOPMENT`
- `APPROVED_FOR_QA`
- `APPROVED_FOR_RELEASE`
- `REJECTED`

## Rules By State

- `WAITING`: no work beyond clarifying missing information.
- `APPROVED_FOR_DISCOVERY`: research and opportunity framing may proceed; no PRD commitment or code.
- `APPROVED_FOR_DESIGN`: design brief, flows, and UX states may be produced.
- `APPROVED_FOR_ARCHITECTURE`: architecture, data contracts, integration notes, and technical risks may be produced.
- `APPROVED_FOR_BACKLOG`: Jira-ready ticket drafts may be produced or real Jira issues may be created when explicitly requested.
- `APPROVED_FOR_DEVELOPMENT`: implementation may begin only in the target product repository and only for approved ticket scope.
- `APPROVED_FOR_QA`: QA validation and automation may proceed.
- `APPROVED_FOR_RELEASE`: release preparation and deployment may proceed when release gates pass.
- `REJECTED`: stop the workflow and document the reason.

## Approval Record Format

Each approval should include:

- Status
- Scope
- Source artifacts
- Jira issue keys when available
- Target repository when development is involved
- Owner or approver
- Date
- Risks accepted
- Conditions or exclusions

## Hard Stops

- No code before `APPROVED_FOR_DEVELOPMENT`.
- No release before `APPROVED_FOR_RELEASE`.
- No real Jira issue creation unless explicitly approved or directly requested.
- No destructive GitHub operation without explicit user approval.
