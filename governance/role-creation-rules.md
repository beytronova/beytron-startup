# Role Creation Rules

Use this file whenever a new Beytron Startup role is added or an existing role is materially changed.

This is the canonical rule set for role creation. If this file conflicts with a shorter instruction elsewhere, this file wins.

## Trigger

Apply these rules when the user asks to add a role such as:

```text
Add a {role-name} role to Beytron Startup.
```

or:

```text
Create a new role for {responsibility/domain/platform}.
```

## Required Approval

Adding or changing a role is a plugin change.

Allowed with normal edit permission:

- Create proposal.
- Create or update role documentation.
- Create or update related skill, checklist, example, or handoff files.
- Update registries and documentation.

Publishing a plugin release still requires:

```text
Approval Status = APPROVED_FOR_RELEASE
```

## Naming Rules

Role slug:

```text
{domain}-{responsibility}
```

Examples:

- `product-analyst`
- `ai-engineer`
- `data-engineer`
- `customer-success`
- `platform-engineer`

Role file path:

```text
roles/{role-slug}.md
```

Primary skill path:

```text
skills/{skill-slug}/SKILL.md
```

Use lowercase kebab-case for all role, skill, workflow, checklist, handoff, and example file names.

## Required Role File

Every new role must create or update:

```text
roles/{role-slug}.md
```

Use `templates/ROLE.template.md`.

Required sections:

- Mission
- Ownership
- Non-Ownership
- Required Inputs
- Workflow Protocol
- Artifact Contracts
- Collaboration Points
- Stop Conditions
- Quality Gates
- Example Prompts

## Required Skill Decision

Every role must have one primary skill.

If an appropriate skill already exists:

- Reference it from `config/role-skill-map.yaml`.
- Do not duplicate the skill.

If no appropriate skill exists, create:

```text
skills/{skill-slug}/SKILL.md
```

Required skill sections:

- Purpose
- Triggers
- Supported Domains or Stacks
- Required Inputs
- Output Standards
- Standards and Rules
- Test or Validation Approach
- Stop Conditions
- Example Prompts

## Required Registry Updates

Update:

```text
config/role-skill-map.yaml
```

The new role entry must include:

- primary skill
- supporting skills
- owned workflows
- expected outputs
- handoff partners

Update `config/workflow-map.yaml` only if the role owns or changes a workflow stage.

Update `config/tool-access.yaml` only if the role requires external tool permissions not already covered.

## Required Workflow Decision

If the role participates in an existing workflow:

- Update the relevant workflow file.
- Add the role as owner, reviewer, consulted role, or handoff receiver.

If the role introduces a new stage, create:

```text
workflows/{workflow-slug}.md
```

A new workflow must define:

- Purpose
- Trigger
- Required Inputs
- Responsible Role
- Required Skills
- Tool Usage
- Outputs
- Checklist Gate
- Approval Gate
- Stop Conditions
- Next Workflow

## Required Handoff Decision

Create or update handoff files when work moves between roles.

Path format:

```text
handoffs/{source-role}-to-{target-role}.md
```

A handoff must define:

- Source role
- Target role
- Required input artifacts
- Expected output artifacts
- Acceptance criteria
- Stop conditions

## Required Checklist Decision

If the role owns a gate or validation step, create:

```text
checklists/{role-or-stage}-checklist.md
```

A checklist must define:

- Required inputs
- Pass criteria
- Block conditions
- Output format
- Next step after pass

## Required Example Decision

If the role changes a user-facing workflow, create or update an example under:

```text
examples/{scenario-name}.md
```

Examples must include:

- Example prompt
- Route
- Required inputs
- Files to read
- Step-by-step execution
- Stop conditions
- Expected final response shape

## Required Validation Scenario Decision

If the role affects routing, approval, tool use, development, release, or security behavior, create or update:

```text
validation/scenarios/{scenario-name}.md
```

Validation scenarios must include:

- Prompt
- Expected route
- Expected reads
- Expected behavior
- Block conditions

## Required Documentation Updates

Always update:

- `CONTRIBUTING.md`
- `CHANGELOG.md`

Update `README.md` when the role changes public usage, structure, or role model.

Update `AGENTS.md` when the role changes mandatory execution order, core rules, or role selection summary.

## Version Impact

Role addition is usually a minor version change.

Use patch only when clarifying an existing role without changing behavior.

Use major when the role changes approval gates, workflow order, or breaks existing role contracts.

## Creation Checklist

Before finishing, verify:

- Role file exists.
- Primary skill exists or is intentionally reused.
- `config/role-skill-map.yaml` references existing files.
- `config/workflow-map.yaml` is updated when workflow ownership changes.
- Handoffs exist when responsibility crosses role boundaries.
- Checklist exists when the role owns a gate.
- Example exists when user-facing behavior changes.
- Validation scenario exists when routing or approval behavior changes.
- Changelog is updated.
- Version impact is stated.

## Final Response Format

```text
Role added: {role-slug}
Primary skill: {skill-slug}
Files created: {list}
Files updated: {list}
Registries updated: {list}
Workflow impact: {none|summary}
Approval impact: {none|summary}
Version impact: {major|minor|patch}
Blockers: {if any}
Next step: {specific action}
```
