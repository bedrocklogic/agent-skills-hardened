---
name: shipping-and-launch
description: Prepare, review, or execute a controlled release when provenance, readiness, promotion, monitoring, rollback, and post-deployment verification are required.
---

# Shipping and Launch

Prepare releases from reviewed source with explicit success, failure, and recovery
criteria. Planning a launch does not authorize executing it.

## Hard authorization boundary

Obtain explicit task-specific authority immediately before committing, pushing,
tagging, publishing, changing remote configuration, deploying, migrating data,
restarting services, changing traffic, or rolling back. Confirm the exact repository,
revision, artifact, environment, and operation. Never infer production authority
from permission to build or test.

Use repository-native, pinned tooling. Do not install a deployment CLI or download
and execute a script during a release unless separately reviewed and authorized.
Never put credentials in command arguments, logs, manifests, or artifacts.

## Readiness

1. Confirm the intended scope and review the complete source diff.
2. Verify the working tree and source revision; reject dirty or ambiguous inputs.
3. Run the documented checks appropriate to the risk and record exact results.
4. Build an immutable artifact once; record its checksum and source revision.
5. Confirm configuration and schema compatibility without copying secret values.
6. Define staged promotion, monitoring signals, stop conditions, and ownership.
7. Prepare a tested rollback or safe roll-forward plan, including data constraints.

## Execution and verification

For an authorized launch, promote only the reviewed artifact. Observe health,
errors, latency, saturation, and the key user path. Stop at the agreed condition;
do not keep retrying a failing rollout without reassessment. Verify the final live
state independently and distinguish deployment success from application behavior.

Report the revision, checksum, target, commands or platform actions performed,
validation evidence, retained artifacts, and rollback readiness. If no live launch
was authorized or performed, say so plainly.
