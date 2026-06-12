# Beytron Startup

Beytron Startup is a Codex plugin blueprint for running an agile AI delivery organization inside product repositories.

It defines reusable roles, workflows, skills, handoffs, templates, and governance rules so Codex can help move any project from idea to delivery with clear responsibilities and quality gates.

## Purpose

- Model a startup delivery organization as AI-readable roles.
- Make product, design, architecture, development, QA, automation, release, growth, and security responsibilities explicit.
- Standardize handoffs between roles.
- Keep implementation tied to PRD, architecture, Jira tickets, approval, tests, and release notes.

## Structure

```text
.codex-plugin/plugin.json
AGENTS.md
roles/
workflows/
skills/
handoffs/
templates/
governance/
```

## Core Flow

```text
Idea -> Discovery -> PRD -> Design -> Architecture -> Backlog -> Development -> QA -> Release -> Growth
```

## Role Model

Each role defines:

- Mission
- Responsibilities
- Required Inputs
- Outputs
- Reads From
- Writes To
- Collaborates With
- Stop Conditions
- Quality Gates
- Example Prompts

## Plugin Usage

Use this repository as a Codex plugin source. Product repositories should keep their own project files, while this plugin supplies the operating model and role behavior.
