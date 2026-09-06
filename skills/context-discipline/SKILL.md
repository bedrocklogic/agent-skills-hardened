---
name: context-discipline
description: Curate engineering-task context to prevent irrelevant history, unrelated systems, and stale assumptions from distorting current work.
---

# Context Discipline

Include a piece of context only if it changes what the agent must inspect, do,
decide, or report.

## Selection rules

- Preserve all explicit current instructions; context reduction never discards or
  weakens them.
- Distinguish active requirements from historical explanation, rejected options,
  and resolved issues.
- Treat a resolved issue as resolved unless new evidence makes it relevant.
- Prefer current repository state, authoritative project documents, and fresh
  verification over stale conversational assumptions.
- Load the target files, their relevant callers or tests, and the smallest useful
  project-specific guidance; do not pull unrelated subsystems into the task.
- Keep other projects, hosts, technologies, and old concerns out unless they alter a
  current boundary or acceptance criterion.
- Surface missing context only when it blocks a correct decision or would make a
  material assumption unsafe.

For long histories, preserve the current objective, constraints, decisions,
evidence, remaining work, and unresolved blockers. Compress failed attempts and
superseded details into the smallest conclusion needed to avoid repeating them.
Do not repeat settled warnings unless the current action reaches that risk again.

Do not impose arbitrary context-size thresholds, automatically fetch remote data,
attach to browsers, load integrations, create rules files, or transmit context to
external models. When sources conflict, identify the conflict and use instruction
authority plus current evidence; ask only if the unresolved choice materially
changes the result.
