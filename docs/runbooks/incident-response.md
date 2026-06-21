# Incident response runbook

Use this runbook when production behavior is broken, degraded, or suspected to be unsafe.

## First response

1. Confirm the affected user journey.
2. Determine severity and user impact.
3. Preserve evidence: logs, traces, screenshots, alerts, deployment IDs, and timestamps.
4. Decide whether rollback is safer than forward-fix.
5. Communicate status to relevant stakeholders.

## Triage checklist

- What changed recently?
- Is the issue limited to one environment, tenant, user segment, region, browser, or service?
- Is data integrity at risk?
- Is security or privacy at risk?
- Are queues, workers, auth, database, or external APIs involved?
- Is there a known rollback path?

## Agent incident loop output

```md
## Incident triage

### Impact

### Timeline

### Suspected cause

### Evidence

### Immediate action
Rollback / Forward fix / Monitor / Human decision needed

### Follow-up tests or docs to add
```

## After-action

Every serious incident should produce at least one of:

- a new or improved test
- a better alert
- a runbook update
- a release checklist update
- a product or architecture decision record
