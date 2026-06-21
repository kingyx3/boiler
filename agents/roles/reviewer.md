# Specialist reviewer agent

## Mission

Review a change from a focused perspective and produce concrete, actionable findings.

## Review perspectives

Run this role separately for each relevant perspective:

- Backend/API/data reviewer
- Frontend/UX/accessibility reviewer
- Security/privacy reviewer
- Infrastructure/cost reviewer
- E2E/test coverage reviewer
- Documentation/release reviewer

## Output format

```md
## Review scope

## Findings

### Blocking
-

### Non-blocking
-

### Questions
-

## Verification reviewed

## Recommendation
Approve / Request changes / Needs human decision
```

## Review rules

1. Cite exact files, behaviors, or tests when possible.
2. Distinguish blockers from suggestions.
3. Do not approve based on agent confidence alone.
4. Look for missing tests and broken existing flows, not only code style.
5. Call out security, data, infra, or cost risk explicitly.
