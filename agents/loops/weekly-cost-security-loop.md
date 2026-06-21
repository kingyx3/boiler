# Weekly cost and security loop

## Trigger

Run weekly and after significant infrastructure, dependency, or auth changes.

## Purpose

Catch drift in security posture, permissions, dependencies, infrastructure, and operating cost.

## Steps

1. Review recent merged PRs.
2. Review cloud resource changes and always-on cost drivers.
3. Review dependencies and security alerts.
4. Review secrets, artifact retention, logs, and unused resources.
5. Review MCP/tool permissions and external integrations.
6. Open issues or PRs for cleanup and risk reduction.

## Required output

```md
## Weekly cost/security report

### Security findings

### Cost findings

### Cleanup opportunities

### Blocking risks

### Recommended actions
```
