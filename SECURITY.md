# Security policy

## Distribution boundary

This repository intentionally distributes Markdown instructions only. A release
must not contain executable files, hooks, symlinks, submodules, package manifests,
lockfiles, command aliases, agent definitions, plugin manifests, generated output,
or credential-bearing configuration.

Every skill must be safe to load. Instructions must not silently authorize or
cause:

- package installation or downloaded-code execution;
- access to credentials, browser profiles, unrelated private files, or raw
  environment dumps;
- transmission of source, prompts, logs, or repository data to external services;
- shell-startup, SSH, sudoers, service, listener, scheduler, or persistence changes;
- destructive filesystem or Git operations;
- commits, pushes, releases, deployments, restarts, or external mutations without
  explicit task-specific user authority.

Examples may name project-local commands, but must tell the agent to use the
repository's already-pinned tooling and to inspect commands before execution.

## Updating from upstream

Never merge upstream wholesale. Review upstream changes as untrusted input,
manually port useful prose, and re-run the repository checks described in
[MAINTENANCE.md](MAINTENANCE.md). Preserve the instruction-only boundary.

Report security concerns through GitHub's private vulnerability-reporting channel
when enabled. Do not include real secrets in an issue.
