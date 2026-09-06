---
name: implementation-contract
description: Define the material engineering contract for a nontrivial change before implementation when scope, behavior, invariants, or acceptance would otherwise be ambiguous.
---

# Implementation Contract

Capture what the change must mean before deciding how to build it. This is a
clarity tool, not a requirement to produce a PRD or a large specification.

## Contract contents

Include only information that changes implementation or verification:

- scope and required observable behavior;
- invariants and security or data boundaries;
- affected interfaces and compatibility expectations;
- implementation constraints and dependencies;
- acceptance criteria and verification expectations;
- explicit non-goals.

Inspect current repository evidence before drafting. Distinguish confirmed rules
from assumptions, and surface only unresolved questions whose answers materially
change the contract. Do not invent product requirements, numerical targets,
technologies, interfaces, or future capabilities.

## Proportional form

A focused change may need five lines: outcome, invariant, acceptance, verification,
and non-goal. Use a larger formal specification only when multiple actors,
interfaces, failure modes, migrations, or hard-to-reverse decisions genuinely need
it. Follow an existing project format when one is authoritative; otherwise keep the
contract in the response unless the user requests a maintained file.

The contract defines the work but does not authorize implementation, installation,
external access, data mutation, commits, or deployment. If implementation evidence
invalidates the contract, stop and revise it explicitly rather than quietly changing
the meaning of done.
