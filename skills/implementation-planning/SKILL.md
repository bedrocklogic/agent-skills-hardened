---
name: implementation-planning
description: Turn a defined engineering task into a concise implementation plan when dependencies, sequencing, risk, or verification are not obvious.
---

# Implementation Planning

Plan how to perform a defined task. This skill does not discover product strategy or
turn a focused change into a roadmap.

## Method

1. State the intended observable outcome.
2. Inspect the relevant existing components, tests, contracts, and project rules.
3. Record constraints and dependencies that materially affect implementation.
4. Order the work by real dependency and risk, using coherent implementation slices.
5. Define mechanical and real-behavior verification appropriate to each claimed
   outcome.
6. State acceptance criteria and explicitly excluded work.
7. Surface only unknowns that could materially change the approach.

Use the shortest useful form. A small task may need only a few ordered lines; a
cross-system change may justify phases and decision points. Do not create plan files,
tracker items, branches, or external records unless requested or required by current
project conventions.

Avoid speculative future features, unnecessary abstractions, invented file lists,
arbitrary task-size thresholds, and decomposition that does not improve review or
verification. Mark uncertain paths as tentative rather than presenting fake
precision. The plan must not broaden authority: implementation, commits, network
access, external mutations, and deployment still require the permissions of the
underlying task.

Before execution, confirm that every step contributes to the requested outcome,
dependencies are ordered, verification can support the claims, and non-goals remain
out of scope.
