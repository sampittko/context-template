# Context Template

This directory is a reusable scaffold for a standalone context repo.

It is meant to be copied into a new repository and then customized for the specific context.

## Included Structure

- `SOUL.md` for durable truths
- `raw/` for approved source evidence
- `wiki/` for compiled and authored knowledge
- `artifacts/` for outputs produced by the context
- `contexts/` for optional nested subcontexts
- `AGENTS.md`, `README.md`, and `ARCHITECTURE.md` for operating rules
- `raw/README.md` and `artifacts/README.md` for the default folder semantics

## Customization Steps

1. Rename and rewrite this `README.md` for the real context.
2. Replace the generic source policy in `AGENTS.md` with the real approved surfaces.
3. Add the actual compiler under `scripts/` if the context needs one.
4. Record the first durable truths in `SOUL.md` only when they are explicit enough.
5. Keep `raw/` for inputs, `wiki/` for knowledge, and `artifacts/` for outputs.
6. Adjust `.gitignore` if this context tracks different local surfaces than the default scaffold assumes.

## Default Empty Folders

The template ships with `gitkeep` placeholders so the structure is visible immediately after cloning.
