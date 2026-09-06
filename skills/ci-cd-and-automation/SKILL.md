---
name: ci-cd-and-automation
description: Design or review repository automation and CI/CD pipelines when repeatable validation, artifact provenance, permissions, promotion, or rollback behavior is in scope.
---

# CI/CD and Automation

Build the narrowest pipeline that makes the repository's real acceptance criteria
repeatable. Inspect the existing package manager, lockfile, scripts, deployment
model, and provider configuration before editing automation.

## Authorization and supply-chain boundary

This skill does not authorize creating remote resources, changing repository
settings or secrets, pushing commits, publishing artifacts, deploying, restarting,
or rolling back an environment. Obtain explicit authority immediately before any
external mutation.

Use the committed lockfile and already-approved project commands. Do not introduce
floating actions, package executors, downloaded scripts, or third-party actions
without reviewing and pinning the exact code. Give workflow tokens the minimum
permissions and never expose secrets in arguments, output, caches, artifacts, or
fork-triggered jobs.

## Pipeline shape

1. Reproduce the repository's documented local verification in a clean environment.
2. Fail fast on manifest, formatting, type, lint, and unit checks as applicable.
3. Run integration and end-to-end checks against real boundaries where the claimed
   behavior depends on them.
4. Build once from a reviewed commit; record revision and artifact checksum.
5. Promote the same immutable artifact between environments.
6. Keep production promotion explicitly gated and observable.
7. Define rollback or safe roll-forward behavior before enabling deployment.

## Review criteria

- Triggers and path filters cannot silently skip required checks.
- Caches improve speed without becoming a source of unreviewed executable state.
- Test credentials are isolated from production credentials.
- Logs and artifacts have bounded retention and contain no sensitive data.
- Migrations respect mixed-version operation and irreversible-step controls.
- Concurrency prevents conflicting deploys without hiding queued or cancelled work.
- Failure, cancellation, retry, and rollback outcomes are reported truthfully.

Do not add deployment platforms, preview environments, feature-flag systems, or
release stages without a current requirement.
