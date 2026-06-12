# Product Repository Structure

This document defines the recommended initial structure for a new product repository created from Beytron Startup.

## Minimum Structure

```text
README.md
AGENTS.md
PROJECT_CONTEXT.md
docs/
  PRD.md
  ARCHITECTURE.md
  RELEASE.md
  DECISIONS.md
  SECURITY.md
```

## README.md

Should include:

- Product name
- Product purpose
- Current approval status
- Stack
- Setup instructions when implementation begins
- Links to PRD, architecture, tickets, and release notes

## AGENTS.md

Should include:

- Repository-specific coding rules
- Stack-specific commands
- Test commands
- Approval requirements
- Security and data handling rules
- How this repository uses Beytron Startup

## PROJECT_CONTEXT.md

Should include:

- Business context
- Users
- Problem
- Success metrics
- Non-goals
- Current stage
- Source idea and approval links

## docs/PRD.md

Copied or linked from the approved PRD.

## docs/ARCHITECTURE.md

Copied or linked from the approved architecture.

## docs/RELEASE.md

Initial release plan placeholder with release gates and rollback expectations.

## docs/DECISIONS.md

Architecture and product decision log.

## docs/SECURITY.md

Security notes, data classification, auth assumptions, secrets policy, and known risks.

## Stack-Specific Expansion

Stack-specific app folders should be created only when development approval exists or when the approved template explicitly includes a non-code scaffold.

Development requires:

```text
Approval Status = APPROVED_FOR_DEVELOPMENT
```
