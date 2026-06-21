# Incident loop

## Trigger

Run when alerts, smoke tests, users, or support reports indicate production may be broken.

## Purpose

Triage impact, preserve evidence, recommend rollback or forward fix, and create follow-up prevention work.

## Steps

1. Identify affected journey and severity.
2. Capture timeline, logs, traces, screenshots, and recent deploys.
3. Determine whether rollback is safer than forward fix.
4. Open or update incident issue.
5. Recommend tests, alerts, or runbook updates after resolution.

## Required output

```md
## Incident loop report

### Impact

### Timeline

### Evidence

### Suspected cause

### Recommended action
Rollback / Forward fix / Monitor / Human decision needed

### Prevention follow-up
```
