---
name: project-constraints
description: Identify and preserve a project's existing engineering constraints, invariants, acceptance criteria, and quality gates when a change could affect them.
---

# Project Constraints

Treat the project's demonstrated standards as constraints on the work. Discover
them before editing rather than substituting generic preferences.

## Establish the constraint set

1. Read current user instructions and repository governance files.
2. Inspect the relevant configuration, tests, types, contracts, architecture
   boundaries, CI checks, and acceptance criteria.
3. Separate explicit requirements from conventions inferred from existing code.
4. Resolve conflicts by instruction authority and current repository evidence;
   surface material ambiguity instead of silently choosing.
5. Keep only constraints relevant to the requested change in active context.

## Preserve the bar

- Do not disable, delete, skip, suppress, or lower a check merely to make the task
  pass.
- Do not weaken authorization, validation, typing, error handling, isolation, or
  compatibility invariants to simplify implementation.
- Prefer the project's actual commands and observed behavior over generic best
  practices.
- Do not invent numerical coverage, performance, file-size, timing, or complexity
  thresholds. Use numbers only when the project, user, or verified standard owns
  them.
- Do not impose an unrelated architecture, methodology, branching model, or tool.

If the requested outcome genuinely requires changing an existing invariant, name
the invariant, show the evidence that it exists, explain the consequence, and obtain
the authority appropriate to that change before proceeding. A pre-existing failing
gate is reported as pre-existing; it is not silently normalized or repaired outside
scope.

Completion requires the relevant original gates plus any task-specific acceptance
checks to pass, or a truthful report of what failed and why.
