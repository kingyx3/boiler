# Contract tests

Contract tests verify that producers and consumers agree on API, event, schema, and shared type behavior.

Use this directory when a change affects:

- frontend/backend API contracts
- worker event payloads
- webhook schemas
- generated types
- shared package interfaces

Contract changes should be reviewed for backwards compatibility unless the PR explicitly states that compatibility is not required.
