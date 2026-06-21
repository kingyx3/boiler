# Security checks

This document defines the security evidence expected once executable app code is added.

## Required checks

Future implementation should include checks for:

- committed sensitive values
- dependency risk
- application code risk
- infrastructure configuration risk
- container image risk, if containers are used
- permissions and environment boundaries

## Required docs

When code is added, document:

- authentication model
- authorization model
- data boundaries
- sensitive configuration handling
- third-party integration permissions
- logging rules for sensitive data

## Agent expectations

Security reviewer agents should treat unresolved auth, data boundary, sensitive configuration, or permissions concerns as release blockers unless a human owner explicitly records a waiver.
