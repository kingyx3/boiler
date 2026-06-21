# Rollback runbook

Use this runbook when a release breaks a critical journey, causes unacceptable operational risk, or introduces security/data concerns.

## Rollback decision criteria

Rollback should be strongly considered when:

- login, onboarding, billing, or core product action is broken
- data integrity is at risk
- security or privacy risk is suspected
- error rate or latency breaches acceptable limits
- a forward fix is slower or riskier than reverting

## Rollback steps

1. Identify the release, commit, deployment, migration, or infrastructure change.
2. Confirm whether rollback is code-only, infra-only, data-related, or mixed.
3. Preserve evidence before changing state.
4. Revert or redeploy the last known good version.
5. Run production smoke tests.
6. Confirm metrics recover.
7. Communicate status and next steps.

## After rollback

- Open a follow-up issue or PR.
- Add a regression test.
- Update release or incident runbooks if needed.
- Document root cause and prevention.
