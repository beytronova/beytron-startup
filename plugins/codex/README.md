# Beytron Startup Marketplace Plugin

This directory is a marketplace-compatible wrapper for Beytron Startup.

Use this path when adding it through Codex's **Add plugin marketplace** dialog:

```text
Source: beytronova/beytron-startup
Git ref: main
Sparse paths: plugins/codex
```

If the shorthand source fails, retry with:

```text
Source: https://github.com/beytronova/beytron-startup.git
Git ref: main
Sparse paths: plugins/codex
```

With the sparse path applied, this directory becomes the marketplace root. The supported manifest is:

```text
.codex-plugin/plugin.json
```

The manifest uses the supported Codex plugin schema and points Codex to the wrapper skill directory:

```text
skills/
```

The canonical source repository remains:

```text
https://github.com/beytronova/beytron-startup
```

The full operating model is documented in the repository root:

- `AGENTS.md`
- `README.md`
- `USAGE.md`
- `governance/approval-statuses.md`
- `config/approval-statuses.yaml`
- `config/workflow-map.yaml`
- `config/role-skill-map.yaml`
- `skills/`
- `roles/`
- `workflows/`
