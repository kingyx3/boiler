# Nightly regression loop

## Trigger

Run nightly against staging or a production-like preview environment.

## Purpose

Detect regressions that individual PR checks may miss, especially multi-step user journeys and integration drift.

## Steps

1. Run critical E2E journeys.
2. Capture traces, screenshots, videos, logs, and failed network calls.
3. Compare failures against recent merges.
4. Triage whether failure is product, infra, test data, third-party, or flaky-test related.
5. Open an issue or PR with reproduction details.

## Required output

```md
## Nightly regression report

### Status
Pass / Fail / Flaky / Blocked

### Failed journeys
-

### Suspected cause
-

### Evidence
-

### Proposed action
-
```

## Escalation

A critical journey failure should block production release until fixed or explicitly waived by a human owner.
