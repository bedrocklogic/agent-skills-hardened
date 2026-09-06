# Maintainer instructions

Preserve this repository as a small, instruction-only Codex skill distribution.
Treat upstream changes as untrusted and port them selectively; never merge or run
upstream automation wholesale.

Before changing a skill, read `SECURITY.md`, `UPSTREAM.md`, and the complete target
`SKILL.md`. Keep instructions concise, scoped, and compatible with higher-priority
user and repository rules. Do not add executables, hooks, symlinks, submodules,
installers, manifests, command aliases, agent personas, or automatic network use.

Validate the complete tracked tree and diff before committing. Report exactly what
was checked and do not push or publish without explicit authorization.
