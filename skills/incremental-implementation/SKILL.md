---
name: incremental-implementation
description: Execute a multi-step engineering change in coherent, reviewable slices that each reach a sound verified state before further work proceeds.
---

# Incremental Implementation

Use slices to control risk, not to manufacture activity. A slice is the smallest
coherent unit that delivers or proves meaningful behavior and can be reviewed on
its own; it may cross several layers when the behavior requires that.

## Slice cycle

1. Select the smallest coherent slice from the intended outcome and dependencies.
2. State what the slice will establish and what remains outside it.
3. Implement only that slice using existing project patterns.
4. Run the relevant mechanical checks: types, lint, build, focused tests, or other
   repository gates.
5. Verify real behavior at the boundary the slice claims to affect when applicable.
6. Review the diff for correctness, scope, failure behavior, and unnecessary
   complexity.
7. Fix supported findings and repeat affected checks.
8. Continue only when the slice is sound and the remaining plan is still supported
   by evidence.

Keep failures, cancellation, partial completion, and unverified outcomes truthful.
If evidence contradicts the plan or exposes a missing requirement, stop the sequence,
preserve the evidence, and revise or request direction rather than building further
on a false assumption.

Do not fragment work into arbitrary line-count, file-count, or time-boxed
micro-steps. Do not add feature flags, abstractions, commits, or infrastructure just
to create slice boundaries. A slice does not authorize committing, pushing,
deploying, or modifying external systems. Avoid unrelated cleanup and report
anything noticed outside scope separately.
