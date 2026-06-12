# Expected Validation Output Format

Codex should use this structure when responding to validation scenarios.

```text
Scenario: {name}
Result: PASS|BLOCKED|FAIL
Route used: {stage -> workflow}
Role used: {role}
Skill used: {skill}
Files that should be read: {list}
Checklist used: {checklist}
Approval status: {status}
Actions allowed: {list}
Actions blocked: {list}
Artifacts expected: {list}
Stop condition triggered: {yes/no and reason}
Next step: {specific action}
```

## PASS

Use `PASS` when the scenario can proceed under current approval and required inputs.

## BLOCKED

Use `BLOCKED` when the system correctly stops due to missing approval, missing artifacts, unclear scope, missing security data, or unavailable tool access.

## FAIL

Use `FAIL` only when evaluating a prior Codex response that violated the rules.
