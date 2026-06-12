# Contributing

This guide defines how to safely change Beytron Startup roles, skills, workflows, templates, checklists, examples, integrations, and governance.

## Contribution Principles

- Preserve the operating model: idea, discovery, PRD, design, architecture, backlog, development, QA, release, growth.
- Do not allow coding directly from an idea.
- Keep approval gates explicit.
- Keep tool side effects explicit and permissioned.
- Keep all outputs traceable to source artifacts.
- Prefer extending existing patterns before creating new structures.

## Before Changing Files

Read the relevant files first:

- `AGENTS.md`
- `README.md`
- `config/workflow-map.yaml`
- `config/role-skill-map.yaml`
- `config/tool-access.yaml`
- Related workflow, role, skill, checklist, integration, template, or example files
- `RELEASE_POLICY.md`
- `CHANGELOG.md`

## Adding or Updating a Role

A role file should define:

- Mission
- Ownership
- Required inputs
- Workflow protocol
- Artifact contracts
- Collaboration points
- Stop conditions
- Quality gates
- Example prompts

When adding a role, also update:

- `config/role-skill-map.yaml`
- Relevant workflows
- Relevant handoffs
- README or examples when user-facing behavior changes
- `CHANGELOG.md`

## Adding or Updating a Skill

A skill should define:

- Purpose and triggers
- Supported stacks or domains
- Required inputs
- Output standards
- Coding or artifact standards
- Test approach
- Stop conditions
- Example prompts

When adding a skill, also update:

- `config/role-skill-map.yaml`
- `config/workflow-map.yaml` when the skill changes routing
- Stack deep dives when the skill supports implementation
- Examples when the skill is used in a golden path
- `CHANGELOG.md`

## Adding a Stack Deep Dive

Place stack deep dives under:

```text
skills/{skill-name}/stacks/{stack-name}.md
```

A stack deep dive should define:

- Stack signals
- Primary language
- File structure rules
- Architecture rules
- Testing commands
- Build commands
- Common mistakes
- Stop conditions

Also update the parent `SKILL.md` and stack `README.md`.

## Adding or Updating a Workflow

A workflow should define:

- Purpose
- Trigger
- Required inputs
- Responsible role
- Required skills
- Tool usage
- Outputs
- Checklist gate
- Approval gate
- Stop conditions
- Next workflow

When changing workflow behavior, update:

- `config/workflow-map.yaml`
- Relevant roles and skills
- Relevant checklists
- Relevant examples
- `CHANGELOG.md`

## Adding or Updating an Integration

An integration file should include:

- Purpose
- Required access
- Authentication
- Inputs
- Outputs
- Workflow usage
- Failure handling

Rules:

- Do not hide side effects.
- State when explicit approval is required.
- Define fallback behavior when the tool is unavailable.
- Update `config/tool-access.yaml`.

## Adding or Updating a Checklist

A checklist should be actionable and produce a pass/block result.

Include:

- Required inputs
- Pass criteria
- Block conditions
- Output format
- Next step after pass

If the checklist gates a workflow transition, update `AGENTS.md` and the relevant workflow.

## Adding or Updating an Example

Examples should show a complete usable path.

Include:

- Example user prompt
- Route
- Required inputs
- Files to read
- Step-by-step execution
- Stop conditions
- Expected final response shape

Examples must not bypass approval, governance, checklists, or target repository `AGENTS.md` instructions.

## Pull Request Checklist

Before submitting a change, verify:

- Changed files match existing structure and naming.
- Registries reference existing files.
- New files are linked from README, roadmap, registry, parent index, or relevant workflow.
- Approval rules remain intact.
- Stop conditions are explicit.
- `CHANGELOG.md` is updated for user-visible changes.
- Version impact is identified as major, minor, or patch.

## Commit and PR Guidance

Use concise commits that describe the operating model change.

Good examples:

```text
Add FastAPI backend stack deep dive
Add Jira ticket to PR golden path example
Document release approval policy
```

PR descriptions should include:

- Summary
- Version impact
- Files changed
- Routing or governance impact
- Verification performed
- Risks and follow-ups
