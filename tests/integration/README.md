# Integration tests

Integration tests verify behavior across service, database, queue, API, or external-boundary layers.

Use this directory for tests that are slower than unit tests but faster and more focused than full browser E2E tests.

Examples:

- API route plus database persistence
- worker consuming a queued job
- auth middleware plus protected endpoint
- webhook parsing and idempotency
