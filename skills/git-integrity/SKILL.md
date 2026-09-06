---
name: git-integrity
description: Preserve trustworthy Git state and history when engineering work involves local changes, staging, commits, branches, remotes, or pushes.
---

# Git Integrity

Use Git as evidence of repository state, not as permission to change it. Follow the
project's existing workflow without imposing trunk-based development, Git Flow,
mandatory feature branches, or another branching model.

## Before modifying

1. Confirm the repository root, current commit and branch or detached state,
   configured remotes, upstream tracking, and working-tree/index status relevant to
   the task.
2. Identify pre-existing modified, staged, and untracked paths. Treat them as user
   work and report them clearly; do not absorb, discard, or rewrite them.
3. Establish the exact requested scope and preserve unrelated changes.

## Before committing

- Commit only when explicitly requested or clearly part of the authorized workflow.
- Inspect every staged path and the complete staged diff.
- Run whitespace, secret, generated-artifact, and task-relevant behavioral checks.
- Keep the commit coherent; do not include temporary files, credentials, build
  output, dependency trees, or unrelated host and repository changes.
- Use a message that truthfully describes the change and intent, following current
  project conventions.

## History and remote safety

Do not rewrite accepted history or force-push unless explicitly authorized for the
exact ref. Prefer non-destructive recovery and additive corrections. Never use a
destructive Git command merely to clean up a state you have not fully inventoried.

After committing, verify the resulting commit and working tree. After an authorized
push, verify the intended local and remote refs when relevant. Report what changed,
what remained pre-existing or untouched, validation performed, and any divergence
or uncertainty. This skill never grants authority to commit, push, delete refs,
publish releases, or change remote configuration.
