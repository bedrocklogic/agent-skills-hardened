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

1. Record the candidate upstream commit.
2. Audit every changed instruction and every added file as untrusted content.
3. Port only useful changes into the curated skills; do not merge wholesale.
4. Confirm each skill remains self-contained and contains no hidden installation,
   network, credential-access, destructive-operation, or external-mutation grant.
5. Confirm the tree contains only `LICENSE`, root Markdown policy/provenance files,
   and `skills/<name>/SKILL.md`.
6. Review the complete diff, scan for secrets and suspicious commands, validate
   skill frontmatter, and install only from the resulting reviewed commit.
