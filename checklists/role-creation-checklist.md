# Role Creation Checklist

Use this checklist before finishing a new role or material role update.

## Required Inputs

- Role name
- Role slug
- Responsibility/domain
- Primary skill decision
- Workflow participation
- Handoff partners
- Expected artifacts
- Approval or tool impact

## Pass Criteria

- `governance/role-creation-rules.md` has been followed.
- `roles/{role-slug}.md` exists.
- Role file uses the required sections.
- Primary skill exists or an existing skill is intentionally reused.
- `config/role-skill-map.yaml` references the role and skill.
- Workflow files are updated when the role owns or changes workflow behavior.
- Handoff files exist when work moves to or from the role.
- Checklist exists when the role owns a gate.
- Example exists when user-facing behavior changes.
- Validation scenario exists when routing, approval, tool use, development, release, or security behavior changes.
- `CHANGELOG.md` is updated.
- Version impact is stated.

## Block Conditions

Block completion if:

- Role file is missing.
- Primary skill is missing and no reuse decision is documented.
- Registry references a missing file.
- Role owns workflow behavior but workflow map is not updated.
- Role creates side effects but tool access is not documented.
- Approval behavior changes without approval status review.
- Changelog is not updated for user-visible behavior.

## Output Format

```text
Role creation checklist: PASS|BLOCKED
Role: {role-slug}
Primary skill: {skill-slug}
Registries updated: {yes|no}
Workflow impact: {none|summary}
Handoff impact: {none|summary}
Validation impact: {none|summary}
Version impact: {major|minor|patch}
Blockers: {list}
```
