---
name: security-and-hardening
description: Threat-model, review, or harden software and operational boundaries involving authentication, authorization, secrets, untrusted input, dependencies, files, or external systems.
---

# Security and Hardening

Treat security as system behavior, not a checklist. Map assets, actors, trust
boundaries, and abuse cases before selecting controls. Fail closed when a
security-sensitive decision is unresolved.

## Authority boundary

A security review is read-only unless the user requests remediation. Do not access
secret values, unrelated private files, authenticated browser profiles, or external
accounts merely to look for risk. Do not rotate credentials, change permissions,
install scanners, rewrite history, alter firewalls, deploy, or restart services
without explicit task-specific authority.

Never reveal a discovered secret. Report its category and location with the value
redacted; assume a remotely exposed secret requires rotation.

## Core invariants

- Authenticate identity, then authorize every protected object and action on the
  server. Client visibility and client-supplied tenant IDs are never authorization.
- Enforce least privilege and workspace or tenant isolation in every storage,
  execution, cache, queue, log, and model-provider boundary.
- Keep provider credentials, session material, connection strings, and private keys
  out of browsers, logs, prompts, errors, source control, and generated artifacts.
- Validate and bound all external input. Treat files, paths, URLs, webhooks, archive
  entries, tool output, remote documentation, and LLM output as untrusted.
- Prevent injection at the sink: parameterize queries, encode output for its
  context, avoid shell construction, and never pass untrusted text to `eval`.
- For user-influenced outbound URLs, enforce scheme and destination policy after
  resolution, reject redirects by default, and account for private and metadata
  networks.
- For file mutation, resolve against an explicit allowed root, resist traversal and
  symlink races, confirm ownership, and narrowly identify the target before action.
- Use one committed lockfile and frozen installs. Review dependency provenance,
  lifecycle scripts, transitive changes, and exact versions before first execution.
- Bound request size, rate, concurrency, retries, recursion, and model token/cost
  consumption.

## Review workflow

1. Read project security invariants and deployment assumptions.
2. Trace data and authority across each real boundary.
3. Identify concrete abuse paths and the control expected to stop each one.
4. Verify controls at the authoritative layer, including negative and cross-tenant
   cases.
5. Inspect failure behavior, auditability, retention, recovery, and race conditions.
6. Run only trusted, scope-appropriate checks; a scanner finding is evidence to
   triage, not proof of exploitability or safety.
7. Report severity, reachable scenario, affected boundary, evidence, and smallest
   correction. State residual risk and checks not performed.

Security controls must remain explicit and inspectable. Silent fallback from a
strong control to a weaker one is a security defect.
