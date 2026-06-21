# Release readiness loop

## Trigger

Run before staging promotion, production deployment, or any release with meaningful user impact.

## Purpose

Produce a go/no-go recommendation grounded in tests, docs, risk review, and rollback readiness.

## Steps

1. Confirm required CI checks are green.
2. Confirm affected user journeys have test evidence.
3. Review unresolved PR comments and specialist findings.
4. Review security, data, infra, and cost impact.
5. Confirm deploy and rollback runbooks are sufficient.
6. Confirm monitoring and smoke tests.

## Required output

```md
## Release readiness

### Recommendation
Go / No-go / Human decision needed

### Evidence

### Risks

### Rollback path

### Post-release checks
```
