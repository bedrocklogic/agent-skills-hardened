---
name: observability-and-instrumentation
description: Design or review logs, metrics, traces, correlation, and operational signals for behavior that must be diagnosable across runtime boundaries.
---

# Observability and Instrumentation

Instrumentation should answer concrete operational questions. Inspect existing
telemetry conventions, data classification, retention, and incident workflows
before adding new fields or vendors.

## Privacy and authority

Never log credentials, tokens, cookies, authorization headers, raw prompts, full
request bodies, or unnecessary personal data. Prefer allowlisted structured fields
and stable identifiers with documented sensitivity. This skill does not authorize
sending telemetry to a new service, changing retention, creating alerts, or
modifying production.

## Workflow

1. Write the questions an operator must answer for the feature or failure.
2. Identify runtime boundaries and define a correlation identifier at the entry
   point; propagate it without trusting a caller to grant authority.
3. Emit structured events at state transitions and failures, not noisy narration.
4. Record outcome, duration, retry/cancellation state, and bounded error category.
5. Choose metrics with stable, low-cardinality dimensions.
6. Trace cross-process work where causal ordering cannot be reconstructed reliably
   from logs alone.
7. Define alerts from user or service impact, with ownership and a useful response.
8. Verify emitted telemetry in the real execution path and test redaction.

Correlation is an architectural requirement for asynchronous or multi-service
flows. It does not replace entry-point identity, workspace isolation, or
authorization checks. Avoid identifiers and error strings that create unbounded
cardinality or disclose tenant data.

Report what signals were observed and where. Do not claim production visibility
from local logger tests alone.
