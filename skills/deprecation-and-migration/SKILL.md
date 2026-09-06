---
name: deprecation-and-migration
description: Plan or review compatible API, dependency, schema, or data migrations where staged rollout, preservation, and rollback constraints matter.
---

# Deprecation and Migration

Migrate from an observed current state to a defined target while keeping every
required intermediate state valid. Inspect real consumers, stored data, deployment
topology, and repository migration conventions first.

## Authority and data safety

Planning or writing a migration does not authorize running it, changing production
data, deleting compatibility code, publishing a package, or deploying. Do not
install ad hoc migration tools. Use project-pinned tooling and obtain explicit
authority for irreversible or externally mutating steps.

## Method

1. Inventory producers, consumers, data volume, version skew, and ownership.
2. Define compatibility requirements and observable completion criteria.
3. Prefer expand/migrate/switch/contract phases over in-place breaking changes.
4. Make retries idempotent and progress observable; record partial-failure behavior.
5. Validate backups and restoration where data loss is possible.
6. Test old and new application versions against each intermediate schema or
   contract when rolling deployment creates version overlap.
7. Separate destructive cleanup from the change that first adopts the new shape.
8. Remove the old path only after evidence shows no supported consumer uses it.

A down migration is not automatically safe. For lossy transformations, document
why reversal cannot restore the original data and prefer a tested forward recovery
or restored backup. Large indexes, backfills, locks, and dual writes require
database-specific analysis rather than generic commands.

Report what was inspected, what was simulated or executed, and what remains
unverified. Do not claim migration success from source inspection alone.
