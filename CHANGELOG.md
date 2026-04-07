# Changelog

Current template version: `2`

Versioning rule:

1. Increment the template version by `1` for each committed template change.
2. Add a dated entry for each version.
3. If a repo has no declared adopted version yet, treat it as version `1` for migration purposes.

## Version 2 - 2026-04-07

This template now prefers a numbered root hierarchy centered on:

1. `1-raw/`
2. `2-wiki/`
3. `3-artifacts/`

### Changed

- Top-level `contexts/` was removed from the default scaffold.
- Imported context repos or context exports now belong under `1-raw/contexts/` when they are inputs to the current context.
- Top-level `scripts/` was renamed to `_scripts/` so operational tooling stays outside the semantic flow without being confused for a core layer.
- The three primary root directories are now explicitly numbered to reinforce the intended working order.
- Documentation now treats imported contexts as source surfaces, not as parallel active subcontexts of the same repo.

### Migration

1. Rename `raw/` to `1-raw/`, `wiki/` to `2-wiki/`, and `artifacts/` to `3-artifacts/`.
2. Rename `scripts/` to `_scripts/`.
3. Update commands such as `node scripts/compile-wiki.mjs` to `node _scripts/compile-wiki.mjs`.
4. Move any input-only nested context from `contexts/<name>/` to `1-raw/contexts/<name>/`.
5. Update `.gitignore`, docs, and source-policy references to the numbered root paths.

### Important Caveat

Do not mechanically move a fully active nested child context into `1-raw/` if it still needs its own authoring lifecycle, output boundaries, or independent commits.

In that case, choose one of these paths:

1. Keep the old structure temporarily while you split the child context into its own standalone repo.
2. Export or clone only the approved surfaces of that child context into `1-raw/contexts/` and treat them as read-oriented inputs.

## Version 1 - Pre-versioned Baseline

This was the scaffold before explicit template version tracking.

Key traits:

- Root flow used `raw/`, `wiki/`, and `artifacts/` without numeric prefixes.
- Optional nested contexts lived under top-level `contexts/`.
- Local tooling lived under top-level `scripts/`.
- Repos that have not adopted the versioned changelog should usually be treated as version `1`.
