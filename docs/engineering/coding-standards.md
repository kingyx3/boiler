# Coding standards

These standards keep human and agent-written code maintainable.

## General rules

1. Prefer clear, boring code over clever abstractions.
2. Keep changes small enough to review, unless a larger migration is explicitly planned.
3. Name files, functions, and variables for domain meaning, not implementation trivia.
4. Avoid hidden global state and surprising side effects.
5. Validate input at trust boundaries.
6. Return useful, safe errors.
7. Add comments for why something exists, not for obvious syntax.

## Agent-specific rules

1. Read existing patterns before introducing new ones.
2. Do not rewrite unrelated files.
3. Do not remove safeguards to make tests pass.
4. Prefer migrations and compatibility notes when data shape changes.
5. Include verification evidence in PRs.
6. Call out uncertain assumptions instead of encoding them silently.

## Review questions

- Is this change understandable to the next maintainer?
- Are edge cases covered?
- Is behavior tested at the right level?
- Does this create duplicate logic?
- Does this weaken security, observability, or rollback?
