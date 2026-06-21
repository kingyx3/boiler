# Observability standards

A future runnable template should make the system easy to inspect during development, staging validation, release, and incidents.

## Required signals

Executable app code should expose:

- health check endpoint or page
- structured application logs
- request or job correlation identifier
- error reporting path
- basic latency and success/failure metrics
- deployment version or commit identifier

## App expectations

### Web

- visible error states
- client-side error reporting guidance
- route or page health signal where appropriate

### API

- health endpoint
- request logging
- safe error responses
- operation timing where useful

### Worker

- job start and finish logs
- retry count
- failure reason
- dead-letter or failed-job handling guidance

## Environment expectations

- `dev` should favor fast debugging.
- `stg` should validate release behavior.
- `prd` should support incident triage and rollback decisions.

## Agent expectations

Agents reviewing a change should ask:

- Can this behavior be observed if it fails?
- Are failures visible to operators?
- Is there enough evidence to decide whether to roll back or fix forward?
