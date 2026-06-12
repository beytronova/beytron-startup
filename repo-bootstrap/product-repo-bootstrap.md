# Product Repository Bootstrap Flow

Use this flow when an incubator idea is approved for repository creation.

## Trigger

```text
Approval Status = APPROVED_FOR_REPO_CREATION
```

## Required Inputs

- Idea slug
- Product name
- Repository owner
- Repository visibility
- PRD
- Architecture
- Ticket drafts
- Approval artifact
- Intended stack
- Initial maintainers

## Required Reads

- `repo-bootstrap/README.md`
- `repo-bootstrap/product-repo-structure.md`
- `templates/PRODUCT_REPO_BOOTSTRAP.template.md`
- `checklists/repo-bootstrap-checklist.md`
- `playbooks/github-execution.md`
- `integrations/github.md`

## Planning Output

Before creating a repository, produce a bootstrap proposal with:

- Repository name
- Repository owner
- Visibility
- Product purpose
- Source idea link
- PRD link
- Architecture link
- Ticket draft link
- Approval status
- Stack
- Initial files
- Branch strategy
- Required secrets and environments
- Initial GitHub settings
- Risks and open questions

## Repository Creation Rules

Allowed only when:

- Approval status is `APPROVED_FOR_REPO_CREATION`.
- User explicitly asks to create the repository.
- Bootstrap checklist passes.
- GitHub access permits repository creation.

Do not create:

- Product code beyond approved scaffold files.
- `src/` unless the approved template and stack require it for a product repo scaffold.
- Secrets or credentials.
- Production deployments.

## Initial Repository Files

Recommended minimum:

- `README.md`
- `AGENTS.md`
- `PROJECT_CONTEXT.md`
- `docs/PRD.md`
- `docs/ARCHITECTURE.md`
- `docs/RELEASE.md`
- `docs/DECISIONS.md`
- `docs/SECURITY.md`
- `.gitignore`

## Post-Creation Output

After creation, report:

- Repository URL
- Files created
- Source artifacts linked
- Required next approvals
- Development readiness status
- Remaining blockers

Development still requires:

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
```
