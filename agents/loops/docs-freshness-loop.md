# Docs freshness loop

## Trigger

Run on PRs that change behavior and weekly for broad drift review.

## Purpose

Keep repo-native documentation aligned with implementation and product reality.

## Steps

1. Review recent code changes.
2. Identify affected product, architecture, engineering, or runbook docs.
3. Compare docs against current behavior and tests.
4. Check whether external Notion/Confluence requirements have been mirrored into Git when release-critical.
5. Open a PR or issue for missing updates.

## Required output

```md
## Docs freshness report

### Stale or missing docs

### Conflicting docs

### Recommended updates

### Release-critical gaps
```
