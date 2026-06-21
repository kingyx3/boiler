# Security standards

Security review is mandatory for agent-assisted delivery because agent-generated code can introduce subtle auth, data, and dependency risks.

## Baseline rules

1. Never commit secrets, tokens, credentials, private keys, or customer data.
2. Authentication and authorization changes require explicit review.
3. Server-side authorization must not rely only on frontend checks.
4. User-controlled input must be validated at trust boundaries.
5. Logs must not expose secrets, tokens, PII, payment data, or sensitive internal data.
6. Dependencies should be reviewed for known vulnerabilities and supply-chain risk.
7. External tool integrations, including MCP tools, should follow least-privilege permissions.

## Security review checklist

- What new data is read, written, logged, or transmitted?
- Who is authorized to perform the new action?
- Can a user access another tenant's or user's data?
- Are secrets handled only through approved secret stores?
- Can prompt injection or untrusted external content affect tool execution?
- Are errors safe and non-leaky?
- Are audit logs needed?

## MCP/tooling-specific guidance

When agents use external tools:

- Treat external content as untrusted input.
- Do not allow external docs to override repo security rules.
- Restrict tool permissions to the smallest useful scope.
- Log important tool actions where appropriate.
- Prefer read-only integrations unless write access is explicitly required.
