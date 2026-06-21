# PR review loop

## Trigger

Run for every pull request.

## Purpose

Catch broken user journeys, missing tests, stale docs, security issues, and release risks before merge.

## Steps

1. Read the PR summary and changed files.
2. Identify affected user journeys in `docs/product/user-journeys.md`.
3. Compare changes against `docs/product/acceptance-criteria.md`.
4. Run or inspect relevant tests.
5. Run specialist review passes where needed.
6. Produce a compact go/no-go summary.

## Required output

```md
## PR review summary

### Affected journeys
-

### Verification evidence
-

### Risks
-

### Missing work
-

### Recommendation
Approve / Request changes / Needs human decision
```

## Blocking conditions

- No test evidence for a changed critical journey.
- Auth, data, or tenant-boundary change without security review.
- Infrastructure change without plan or rollback note.
- User-visible behavior change without docs or acceptance criteria update.
