# Execution Playbooks

Execution playbooks define how Codex should use external systems after routing, approval, and governance have been checked.

Playbooks are more operational than integration contracts. They describe concrete action sequences, required evidence, failure handling, and final output format.

## Available Playbooks

- `jira-execution.md`: read, create, update, and transition Jira issues safely.
- `github-execution.md`: inspect repositories, create branches, commit changes, open pull requests, and report status safely.
- `jira-github-delivery.md`: connect approved Jira tickets to GitHub implementation and PR delivery.

## Rules

- Always read `config/tool-access.yaml` before external tool use.
- Always read the matching file under `integrations/` before side effects.
- Side effects require explicit approval or workflow permission.
- Never create duplicate Jira issues or GitHub PRs without checking existing work.
- Capture tool outputs in the final response or artifact.
