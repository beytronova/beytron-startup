# Beytron Startup Marketplace Plugin

This directory is the recommended marketplace-compatible wrapper for Beytron Startup.

Use this path when adding it through Codex's **Add plugin marketplace** dialog:

```text
Source: https://github.com/beytronova/beytron-startup.git
Git ref: main
Sparse paths: plugins/beytron-startup
```

With the sparse path applied, this directory becomes the marketplace root. The supported manifest is:

```text
.codex-plugin/plugin.json
```

The manifest uses the supported Codex plugin schema and points Codex to:

```text
skills/
```

The canonical source repository remains:

```text
https://github.com/beytronova/beytron-startup
```
