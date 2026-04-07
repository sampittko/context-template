# Working Model

This repo is a composable context repo.

It usually operates in three working layers:

1. `1-raw/` is the source-of-truth ingest layer.
2. `2-wiki/` is the compiled and authored knowledge layer.
3. `3-artifacts/` holds outputs produced by this context.

Optional support surfaces:

- `1-raw/contexts/` can hold imported context repos or context exports used as inputs to this context.
- `_scripts/` can hold local tooling that supports the repo without becoming part of the semantic layer flow.

Default workflow for a new session:

1. Start at the repo root with `SOUL.md`.
2. Read `CHANGELOG.md` to confirm the current template version and any recent structural changes that affect navigation or migration.
3. Read the matching concept or derived index when it exists.
4. Then read `2-wiki/index.md` and `2-wiki/sources/index.md` when they exist.
5. Fall back to approved `1-raw/` surfaces only when the compiled layer is missing needed detail.

Operational rules:

1. `SOUL.md` is the highest-authority statement of intent for this context.
2. `1-raw/` is input evidence. `2-wiki/` is interpretation and reusable knowledge. `3-artifacts/` is for outputs produced by this context.
3. `_scripts/` is tooling, not part of the reasoning-layer hierarchy.
4. `1-raw/contexts/` is for imported context inputs, not for parallel active workspaces inside this repo.
5. Do not place produced outputs into `1-raw/` unless they are explicitly promoted later as new source material.
6. Let this context's local docs determine how deep to go. Default to `2-wiki/` before `1-raw/`.
7. Prefer `2-wiki/concepts/` and `2-wiki/derived/` over `2-wiki/sources/` when they have the needed context.
8. Prefer this context's `2-wiki/` over its `1-raw/` for orientation, navigation, and cross-source context.
9. Treat approved `1-raw/` surfaces as the source of truth for source details if authored layers and raw disagree, unless `SOUL.md` explicitly sets intent.
10. If approved source surfaces were refreshed, or `2-wiki/` is missing or stale, run `node _scripts/compile-wiki.mjs` from the repo root when that script exists.
11. If `1-raw/contexts/` contains another repo or export, treat it as an input surface and avoid mixing current-context authoring into it.
12. `2-wiki/sources/` and `2-wiki/manifests/` are generated outputs inside this context repo.
13. After changing repo structure, source policy, or knowledge-layer docs, run a manual consistency pass across `README.md`, `AGENTS.md`, `SOUL.md`, `ARCHITECTURE.md`, and relevant `2-wiki` entry pages, then correct any drift.
14. `CHANGELOG.md` is the source of truth for template versioning. Check it before making structural assumptions, and increment the version number whenever the template changes.
15. If a context repo does not yet declare an adopted template version, treat it as version `1` for migration planning unless local docs clearly say otherwise.

# Source Policy

Replace this section with the approved source surfaces for the specific context.

Typical source categories:

- `1-raw/websites/<site>/public/`
- `1-raw/documents/<name>/sections/`
- `1-raw/youtube-transcripts/<channel>/*-cleaned.txt`
- `1-raw/manual/*.md`
- `1-raw/projects/<repo>/<approved-surface>`
- `1-raw/contexts/<name>/<approved-surface>`

Until this file is customized, no raw surfaces should be treated as approved by default.
