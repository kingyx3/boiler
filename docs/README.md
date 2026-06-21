# Documentation index

Documentation in this repo is split by how it is used by humans, agents, and CI gates.

## Structure

```txt
docs/
  product/                 # PRDs, user journeys, acceptance criteria
  architecture/            # System diagrams, decisions, service boundaries
  architecture/adr/        # Architecture decision records
  engineering/             # Testing, release, security, cost, coding standards
  runbooks/                # Operational procedures and incident response
```

## Documentation policy

Keep release-critical docs in Git so they can be versioned, reviewed, tested, and changed with the code they govern.

External tools such as Notion or Confluence are useful collaboration surfaces. They should feed approved requirements into this repo, not replace repo-native release criteria.

## When a PR should update docs

A PR should update docs when it changes:

- user-visible behavior
- API behavior
- data models or migrations
- permissions or security posture
- infrastructure, cost, or deployment behavior
- release, rollback, or incident response procedures
- agent instructions or review loops
