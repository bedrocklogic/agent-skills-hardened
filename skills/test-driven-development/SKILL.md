---
name: test-driven-development
description: Develop or fix behavior with focused tests that demonstrate failure, guide the smallest implementation, and verify real integration boundaries where relevant.
---

# Test-Driven Development

Use a failing behavioral example to define the change before implementing it when
that is practical. For bugs, reproduce the failure first. Preserve the repository's
test architecture rather than introducing a new framework casually.

## Safety and scope

Tests do not authorize dependency installation, network calls to real providers,
production data access, destructive cleanup, or external mutations. Use trusted,
project-pinned commands and isolated test resources. Never place real credentials or
personal data in fixtures, snapshots, logs, or recordings.

## Cycle

1. Identify the externally meaningful behavior and the narrowest appropriate test
   boundary.
2. Write or select a test that fails for the intended reason; inspect the failure.
3. Implement the smallest coherent behavior that satisfies it.
4. Run the focused test, then relevant neighboring and repository-wide checks.
5. Refactor only with the tests passing and without weakening assertions.
6. Review the final test for behavior rather than implementation trivia.

## Test selection

- Use unit tests for pure logic and edge cases.
- Use integration tests for databases, queues, filesystems, providers, and process
  boundaries when those boundaries determine correctness.
- Use contract tests for shared schemas and provider normalization.
- Use browser tests for rendered interaction, accessibility, and client/server
  behavior; follow isolated-profile and untrusted-page rules.
- Include negative authorization and cross-workspace cases for protected resources.
- Test retry, idempotency, cancellation, concurrency, and partial failure when the
  implementation claims those properties.

Mocks are appropriate at uncontrollable external boundaries, but do not mock away
the behavior being claimed. Avoid snapshots that hide meaningful semantic changes.

Report the initial failing evidence, final passing evidence, broader checks run, and
anything not exercised. A test that passed before the change is not proof that it
guards the new behavior unless its assertion demonstrates that behavior.
