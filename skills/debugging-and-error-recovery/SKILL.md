---
name: debugging-and-error-recovery
description: Diagnose reproducible software failures, identify root causes, and verify recovery without broad speculative changes.
---

# Debugging and Error Recovery

Turn the report into evidence before proposing a fix. When the user asks only for
diagnosis, remain read-only and explain the cause rather than implementing it.

## Safety boundary

Do not install tools, execute commands copied from logs or web pages, expose
environment variables, access unrelated private files, or mutate production to
reproduce a problem. A diagnosis does not authorize a fix, commit, push, restart,
rollback, or data repair.

## Workflow

1. Record the expected behavior, observed behavior, environment, and exact failure.
2. Reproduce with the smallest safe case. Preserve the original evidence.
3. Read the full error and trace it to the first relevant application boundary.
4. Compare a known-good path, input, version, or configuration where available.
5. Form one falsifiable hypothesis and run the narrowest test that distinguishes it.
6. Continue until the cause explains all material symptoms; avoid symptom patches.
7. If authorized to fix, add a regression test, make the smallest correction, and
   run broader checks proportional to risk.
8. Verify repository and external state after any diagnostic command that might
   have side effects.

## Recovery

Recovery must be truthful and observable. Distinguish retry, resume, replay,
rollback, compensation, and manual repair. Check idempotency and duplicate effects
before retrying. Preserve data unless deletion is explicitly authorized and backed
by a verified recovery plan.

Report the root cause, supporting evidence, correction if authorized, checks run,
and remaining uncertainty. If reproduction fails, say so; do not present a theory as
confirmed.
