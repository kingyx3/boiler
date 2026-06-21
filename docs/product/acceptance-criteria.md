# Acceptance criteria

Acceptance criteria define what must be true before a feature can be considered done.

## Standard format

```md
## Feature: <name>

### User outcome
As a <user>, I can <action>, so that <business value>.

### Acceptance criteria
- Given <state>, when <action>, then <observable outcome>.
- Given <failure mode>, when <action>, then <safe recovery behavior>.

### Verification plan
- Unit:
- Integration:
- E2E:
- Manual or exploratory:
- Monitoring:

### Non-functional requirements
- Security:
- Performance:
- Cost:
- Accessibility:
- Rollback:
```

## Definition of done

A feature is not done until:

1. The expected user outcome is documented.
2. The main happy path is covered by an automated test or there is a reviewed reason why not.
3. Important failure modes are handled and observable.
4. Security, data, cost, and infrastructure impacts are considered.
5. Documentation and release notes are updated where behavior changed.
6. The PR includes verification evidence.
