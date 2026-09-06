---
name: performance-optimization
description: Diagnose and improve measured performance bottlenecks while preserving correctness, security, and maintainability.
---

# Performance Optimization

Optimize a measured user or system problem, not a hunch. Establish a representative
baseline and a success threshold before changing code.

## Safety and scope

Do not install profilers or benchmarking packages, generate uncontrolled load,
query sensitive production data, or change production infrastructure without
explicit authority. Use existing project-pinned tools. Redact profiles and traces;
they may contain URLs, queries, identifiers, or payload data.

## Workflow

1. Define the affected scenario and metric: latency distribution, throughput,
   resource use, bundle cost, responsiveness, or another observable outcome.
2. Reproduce under representative data, hardware, concurrency, and network
   conditions; record variance and warm-up behavior.
3. Profile the end-to-end path and identify the dominant constraint.
4. Change one relevant variable with the smallest maintainable correction.
5. Repeat the same measurement and compare before/after distributions.
6. Run correctness and regression checks; optimization is not allowed to weaken
   authorization, consistency, durability, accessibility, or error reporting.
7. Keep the change only if the measured benefit clears the stated threshold and the
   operational cost is acceptable.

## Common boundaries

- Inspect query plans before adding indexes; account for write and storage cost.
- Bound concurrency at the constrained resource rather than moving the queue.
- Cache only when invalidation, isolation, and staleness semantics are explicit.
- Keep cache keys tenant-aware and never cache permissions or sensitive responses
  under ambiguous identities.
- For browser work, measure representative runtime behavior rather than bundle size
  alone.

Report method, environment, raw summary statistics, observed improvement, tradeoffs,
and untested conditions. Do not claim a production improvement from a synthetic
local benchmark alone.
