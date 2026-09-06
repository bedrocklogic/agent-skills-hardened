---
name: code-simplification
description: Simplify recently changed or explicitly scoped code while preserving behavior, public contracts, security boundaries, and repository conventions.
---

# Code Simplification

Reduce accidental complexity without turning a focused task into a rewrite. Read
the target code, tests, callers, and project conventions before editing.

## Boundaries

- Work only in the user's stated scope or the immediately affected code.
- Preserve behavior, public interfaces, authorization checks, observability, and
  error semantics unless the user explicitly requests a behavior change.
- Do not install tools, rewrite history, commit, push, deploy, or modify external
  systems merely because this skill was loaded.
- Do not simplify generated files or vendored code at the generated output layer.

## Method

1. Establish a passing behavioral baseline or document why one is unavailable.
2. Identify concrete complexity: duplication, needless indirection, tangled state,
   misleading names, unreachable branches, or abstractions with one non-variable
   use.
3. Make one coherent reduction at a time.
4. Prefer explicit data flow and small domain-named helpers over generic frameworks.
5. Remove dead code only after confirming it has no runtime, build, migration, test,
   or operational consumer.
6. Run the narrowest relevant checks after each risky step, then the broader project
   verification appropriate to the change.
7. Review the final diff for behavior drift and unrelated churn.

Do not optimize for fewer lines alone. A simplification is successful when the
result has fewer concepts or branches, remains easy to inspect, and has equivalent
observable behavior. Report exactly what was verified.
