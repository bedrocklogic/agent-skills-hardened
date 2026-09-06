# Approved skill manifest

This manifest records the skills approved for the hardened distribution. The
review baseline identifies the hardened commit at which each skill's contents were
reviewed and approved; later documentation-only commits do not change that skill
baseline.

| Skill | Purpose | Status | Hardened review baseline |
| --- | --- | --- | --- |
| `api-and-interface-design` | Design or review stable, validated interfaces and their authorization and compatibility boundaries. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `browser-testing-with-devtools` | Verify browser-visible behavior with trusted tooling and isolated browser state. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `ci-cd-and-automation` | Design or review repeatable, least-privilege validation and deployment pipelines. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `code-review-and-quality` | Review changes for correctness, security, maintainability, regressions, and evidence gaps. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `code-simplification` | Reduce scoped code complexity while preserving behavior and boundaries. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `context-discipline` | Keep engineering-task context focused on active instructions, current evidence, and material decisions. | approved | `b6353fbd24fdd4b60ccbd5703f99f3d7304ac80e` |
| `debugging-and-error-recovery` | Reproduce failures, determine root causes, and verify safe recovery. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `deprecation-and-migration` | Plan or review compatible, staged API, dependency, schema, and data migrations. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `documentation-and-adrs` | Maintain proportional documentation and records for consequential decisions. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `frontend-ui-engineering` | Implement or review accessible, responsive, design-system-aligned web interfaces. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `git-integrity` | Preserve trustworthy repository state and history across local changes, commits, remotes, and pushes. | approved | `b6353fbd24fdd4b60ccbd5703f99f3d7304ac80e` |
| `incremental-implementation` | Execute multi-step changes as coherent slices with mechanical and real-behavior verification. | approved | `b6353fbd24fdd4b60ccbd5703f99f3d7304ac80e` |
| `implementation-contract` | Define the material scope, behavior, invariants, non-goals, and acceptance contract for a change. | approved | `b6353fbd24fdd4b60ccbd5703f99f3d7304ac80e` |
| `implementation-planning` | Produce a proportional implementation sequence from a defined engineering task. | approved | `b6353fbd24fdd4b60ccbd5703f99f3d7304ac80e` |
| `observability-and-instrumentation` | Design or review privacy-safe logs, metrics, traces, correlation, and alerts. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `performance-optimization` | Diagnose and improve measured bottlenecks without weakening correctness or security. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `project-constraints` | Identify and preserve existing project invariants, quality gates, and acceptance criteria. | approved | `b6353fbd24fdd4b60ccbd5703f99f3d7304ac80e` |
| `security-and-hardening` | Threat-model, review, and harden trust, authorization, secret, input, and supply-chain boundaries. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `shipping-and-launch` | Prepare, review, or execute explicitly authorized releases with provenance and recovery controls. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `source-driven-development` | Resolve changing or uncertain technical behavior using authoritative primary sources. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |
| `test-driven-development` | Guide changes with behavioral tests and real integration-boundary verification. | approved | `201bd1b633d8a3249e1aa9d6422a956160d4c571` |

## Repository invariant

Nothing under `skills/` may contain anything except `SKILL.md` unless a future
explicit security review approves expanding this rule. Approval must precede the
change; the presence of a useful upstream file is not approval.
