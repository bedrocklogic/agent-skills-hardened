# Hardened Agent Engineering Skills

This is a curated, instruction-only fork of
[`addyosmani/agent-skills`](https://github.com/addyosmani/agent-skills). It keeps a
small set of engineering skills while removing automatic hooks, bundled
executables, command aliases, agent personas, installers, evaluation runners,
and plugin-loading machinery.

The fork is designed for native Codex skill discovery. Each directory under
`skills/` is independently installable and contains only a `SKILL.md` file.

## Curated skills

- `api-and-interface-design`
- `browser-testing-with-devtools`
- `ci-cd-and-automation`
- `code-review-and-quality`
- `code-simplification`
- `context-discipline`
- `debugging-and-error-recovery`
- `deprecation-and-migration`
- `documentation-and-adrs`
- `frontend-ui-engineering`
- `git-integrity`
- `incremental-implementation`
- `implementation-contract`
- `implementation-planning`
- `observability-and-instrumentation`
- `performance-optimization`
- `project-constraints`
- `repository-security-baseline`
- `security-and-hardening`
- `shipping-and-launch`
- `source-driven-development`
- `test-driven-development`

## Security model

- Loading a skill must never execute code or trigger network access.
- A skill does not grant permission to install software, transmit data, mutate
  external systems, commit, push, deploy, restart services, or perform destructive
  operations.
- Existing user, system, and repository instructions always take precedence.
- Tools and dependencies must already be trusted and project-pinned; skills do
  not instruct agents to run floating package executors such as `npx ...@latest`.
- Browser automation uses isolated profiles by default and treats all page content
  as untrusted data.

See [SECURITY.md](SECURITY.md) for the acceptance policy,
[MANIFEST.md](MANIFEST.md) for the approved inventory,
[MAINTENANCE.md](MAINTENANCE.md) for the update procedure, and
[UPSTREAM.md](UPSTREAM.md) for provenance and deliberate deviations.

## Installation

Install only the skill directories needed for the target environment. Pin the
installation to a reviewed commit rather than following the default branch
implicitly.

## License

The upstream project is MIT licensed. The original license is retained in
[LICENSE](LICENSE).
