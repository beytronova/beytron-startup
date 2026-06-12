# Scenario: Repo Bootstrap

## Prompt

```text
Use Beytron Startup.
Current stage: repo-bootstrap
Approval Status = APPROVED_FOR_REPO_CREATION
Idea slug: subscription-prediction
Create a product repository proposal. Do not create the repository yet.
```

## Expected Route

```text
incubator idea -> repo bootstrap proposal -> repository creation approval
```

## Expected Reads

- `repo-bootstrap/README.md`
- `repo-bootstrap/product-repo-bootstrap.md`
- `repo-bootstrap/product-repo-structure.md`
- `templates/PRODUCT_REPO_BOOTSTRAP.template.md`
- `checklists/repo-bootstrap-checklist.md`
- `playbooks/github-execution.md`

## Expected Behavior

- Produces repository bootstrap proposal.
- Does not create the repository because the prompt says not yet.
- Identifies required source artifacts.
- Identifies next approval needed for development.

## Block Conditions

- Approval is not `APPROVED_FOR_REPO_CREATION`.
- PRD or architecture is missing.
- Repository owner or visibility is unclear.
