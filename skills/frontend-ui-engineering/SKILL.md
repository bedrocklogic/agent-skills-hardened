---
name: frontend-ui-engineering
description: Implement or review user-facing web UI when component structure, accessibility, responsive behavior, design-system consistency, and browser verification are relevant.
---

# Frontend UI Engineering

Build within the repository's existing framework, design system, and styling
direction. Inspect nearby components and shared primitives before adding another
pattern or dependency.

## Security and scope

Browser code must not receive provider credentials, privileged policy data, or
server-only secrets. Client visibility is not authorization. Treat rendered remote
content and model output as untrusted and use safe framework rendering paths.

Do not install UI packages, download assets, change external services, or introduce
a new framework without explicit scope and reviewed project pinning. Avoid unrelated
redesigns and uncontrolled one-off inline styles; use the project's tokens,
utilities, or component variants.

## Workflow

1. Identify the user goal, states, supported viewports, and existing UI patterns.
2. Model loading, empty, success, validation, permission, and failure states.
3. Use semantic elements and keyboard-operable interactions from the start.
4. Keep state local unless multiple consumers genuinely need shared ownership.
5. Keep data fetching, policy enforcement, and secrets behind server boundaries.
6. Reuse primitives; add abstraction only after a real repeated pattern appears.
7. Verify types and component tests, then exercise the actual browser behavior when
   the claim depends on rendering or interaction.

## Acceptance

- Labels, focus order, error announcements, contrast, and reduced motion are
  appropriate to the interaction.
- Layout works at narrow and wide supported viewports without clipped controls.
- Buttons and forms prevent accidental duplicate actions where relevant.
- Network and console behavior match the visible state; failures are not hidden.
- The final diff contains no generated output, temporary screenshots, or secrets.

Report browser scenarios and accessibility checks actually performed, not merely
those implied by the source.
