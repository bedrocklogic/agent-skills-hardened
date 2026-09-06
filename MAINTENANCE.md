# Maintenance procedure

This repository is curated rather than synchronized. Its current tree must remain
simple enough to audit directly, and upstream content is untrusted until reviewed.

## Safe upstream update process

1. Identify the exact candidate upstream commit and the hardened commit from which
   the comparison starts.
2. Review the exact diff between those commits. Do not rely on release notes,
   repository popularity, filenames, or an upstream security claim as proof.
3. Treat every upstream change—including Markdown instructions—as untrusted.
4. Inspect additions and modifications for:
   - executable content or instructions that download or execute code;
   - hooks, installers, package-manager commands, workflows, or persistence;
   - automatic or unexpected network behavior;
   - credential, cookie, token, private-file, or environment access;
   - transmission of source, prompts, logs, or data to external models or services;
   - destructive filesystem or Git behavior;
   - session injection, automatic context loading, or hidden agent activation.
5. Selectively port only useful skill changes. Never auto-sync, blindly merge, or
   run upstream setup, installation, hook, evaluation, or validation machinery.
6. Preserve the documentation-only repository boundary and the rule that every
   `skills/<name>/` directory contains only `SKILL.md`. Expanding either invariant
   requires a new explicit security review and approval before the change.
7. Read every changed `SKILL.md` completely and confirm that it remains concise,
   self-contained, scoped, and compatible with higher-priority user and repository
   instructions.
8. Validate every approved skill only with an already trusted built-in or native
   validator present in the current Codex environment. Do not download, install,
   or improvise a validator solely for this review. If none is available, stop
   validation and report that fact rather than substituting an unreviewed tool.
   Record the validator identity and version when practical. Validation success
   never overrides a repository security-policy violation. Also inspect the
   complete candidate tree for executables, symlinks, submodules, manifests,
   lockfiles, hooks, installers, workflows, generated files, and secrets.
9. Review the complete staged diff and create a new hardened commit only after all
   checks pass. Record the reviewed upstream commit and update `MANIFEST.md` with
   each changed skill's new hardened review baseline.
10. Verify the published hardened commit and its tree before installation. Update
    installed Codex skills only after the review passes, using that exact hardened
    commit rather than a moving branch.
11. Verify each installed file matches the reviewed hardened commit and that native
    discovery recognizes every installed skill. Report the validation performed and
    any behavior not exercised.

## Ref hygiene

`main` is the only maintained branch. Upstream branches and tags must not be
reintroduced into this fork unless a specific ref is explicitly needed, reviewed,
and approved. Fetching upstream for inspection must not publish upstream refs to the
hardened repository.

Do not rewrite or force-push hardened `main`. If a maintenance review fails, leave
the installed skills unchanged and do not publish the candidate update.
