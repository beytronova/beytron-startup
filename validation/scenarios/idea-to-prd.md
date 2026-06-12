# Scenario: Idea to PRD

## Prompt

```text
Use Beytron Startup.
Current stage: idea
Approval Status = APPROVED_FOR_RESEARCH
Idea: A mobile app that predicts upcoming subscription payments.
Research this and create a PRD. Do not code.
```

## Expected Route

```text
idea -> discovery -> PRD
```

## Expected Reads

- `AGENTS.md`
- `config/workflow-map.yaml`
- `config/role-skill-map.yaml`
- `workflows/idea-to-discovery.md`
- `workflows/discovery-to-prd.md`
- `roles/product.md`
- `skills/product-discovery/SKILL.md`
- `skills/prd-writing/SKILL.md`
- `templates/PRD.template.md`
- `checklists/discovery-checklist.md`
- `checklists/prd-checklist.md`

## Expected Behavior

- Produces research/discovery output.
- Produces or drafts PRD.
- Does not create product code.
- Does not create GitHub repo.
- Does not create Jira issues unless separately approved.

## Pass Condition

Codex returns discovery and PRD artifacts with open questions, risks, and next approval needed.
