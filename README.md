# Context Template

This directory is a reusable scaffold for a standalone context repo.

It is meant to be copied into a new repository and then customized for the specific context.

## Included Structure

- `SOUL.md` for durable truths
- `1-raw/` for approved source evidence, including imported context inputs under `1-raw/contexts/`
- `2-wiki/` for compiled and authored knowledge
- `3-artifacts/` for outputs produced by the context
- `_scripts/` for optional local tooling kept outside the three-layer flow
- `AGENTS.md`, `README.md`, and `ARCHITECTURE.md` for operating rules
- `1-raw/README.md`, `3-artifacts/README.md`, and `_scripts/README.md` for default folder semantics
- `CHANGELOG.md` for template version history and migration notes

## Customization Steps

1. Rename and rewrite this `README.md` for the real context.
2. Replace the generic source policy in `AGENTS.md` with the real approved surfaces.
3. Add the actual compiler under `_scripts/` if the context needs one.
4. Record the first durable truths in `SOUL.md` only when they are explicit enough.
5. Keep the root visually centered on `1-raw/`, `2-wiki/`, and `3-artifacts/`.
6. Put imported context repos or context exports under `1-raw/contexts/` when they are inputs to this context.
7. Adjust `.gitignore` if this context tracks different local surfaces than the default scaffold assumes.
8. Check `CHANGELOG.md` for the current template version when adapting an existing context repo to template changes.

## Default Empty Folders

The template ships with `gitkeep` placeholders and directory READMEs so the structure is visible immediately after cloning.
