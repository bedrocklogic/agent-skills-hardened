# Upstream provenance

- Canonical upstream: `https://github.com/addyosmani/agent-skills`
- Hardened-fork base: `48cb1168aeaaa70dfc2bbf709eddfa2a8ed8129a`
- Base reviewed: 2026-09-06

This repository is a GitHub fork so its relationship to upstream remains visible.
It is not a mirror and does not automatically ingest upstream changes.

Because GitHub forks preserve ancestry, removed upstream files remain visible in
historical commits. Only a specifically reviewed hardened commit tree is approved
for installation; do not execute content from upstream history.

## Deliberate deviations

The hardened fork removes all upstream hooks, scripts, eval runners, plugin and
marketplace metadata, command aliases, agent personas, symlinks, setup material,
and workflow/meta skills. It retains only selected engineering skills and rewrites
them to preserve authorization boundaries, avoid floating tool execution, reduce
context cost, and require evidence-based verification.

## Update procedure

Follow [MAINTENANCE.md](MAINTENANCE.md). It is the authoritative update procedure;
do not duplicate or shorten that process here.
