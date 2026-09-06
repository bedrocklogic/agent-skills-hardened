---
name: documentation-and-adrs
description: Create or update proportional engineering documentation and ADRs when behavior, operation, or consequential decisions would otherwise be unclear.
---

# Documentation and ADRs

Write the smallest durable document that helps its intended reader make a correct
decision. Inspect the implementation and existing documentation hierarchy before
editing; documentation is not proof that behavior exists.

## Source-of-truth discipline

Keep these states distinct:

- implementation plus verification: what exists and works;
- current-status documentation: what has been demonstrated now;
- invariants and ADRs: what constrains implementation and why;
- changelog: meaningful historical evolution;
- plans and research: proposals, not implementation or roadmap commitments.

Do not copy secrets, raw user data, private logs, or sensitive configuration into
documentation. Do not publish, commit, or push documentation without the authority
required for those actions.

## ADR threshold

Use an ADR for a consequential, cross-cutting, or hard-to-reverse decision—not for
routine package additions or obvious implementation details. Follow the repository's
existing location and numbering convention. Capture:

1. context and forces;
2. the decision and its scope;
3. meaningful alternatives considered;
4. reasoning;
5. consequences and follow-up constraints;
6. status and supersession links where applicable.

## Maintenance

Update documentation when a substantive change makes it false or materially
incomplete. Prefer intent, invariants, ownership, recovery, and surprising limits
over narration of obvious code. Avoid speculative future feature lists and repeated
rules that belong in one authoritative location.

Verify commands, paths, versions, examples, and links you change. State explicitly
when an operational procedure has not been exercised in the described environment.
