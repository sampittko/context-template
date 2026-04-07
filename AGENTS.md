# Working Model

This repo is a composable context repo.

It usually operates in three working layers plus optional nested subcontexts:

1. `raw/` is the source-of-truth ingest layer.
2. `wiki/` is the compiled and authored knowledge layer.
3. `artifacts/` holds outputs produced by this context.

Optional composition:

- `contexts/` can hold narrower nested contexts.

Default workflow for a new session:

1. Check which nested contexts exist under `contexts/`.
2. If the target context is unclear and more than one real context is available, ask which context to use. Otherwise, assume the root context.
3. If the root context is selected, start with `SOUL.md`.
4. If a nested context is selected, switch to `contexts/<name>/` and treat that directory as the active context root.
5. In the selected context, read `SOUL.md`, then the matching concept / derived index when it exists.
6. Then read the selected context's `wiki/index.md` and `wiki/sources/index.md` when they exist.
7. Fall back to the approved `raw/` surfaces of the selected context only when the compiled layer is missing needed detail.

Operational rules:

1. `SOUL.md` is the highest-authority statement of intent for the selected context.
2. `raw/` is input evidence. `wiki/` is interpretation and reusable knowledge. `artifacts/` is for outputs produced by this context.
3. Do not place produced outputs into `raw/` unless they are explicitly promoted later as new source material.
4. Before deep reasoning, identify the active context. If it is unclear and more than one real context is available, ask first.
5. Once a context is selected, follow that context's local `AGENTS.md`, `README.md`, and `ARCHITECTURE.md` when they exist.
6. Let the selected context's local docs determine how deep to go. Default to `wiki/` before `raw/`.
7. Prefer context-local `wiki/concepts/` and `wiki/derived/` over `wiki/sources/` when they have the needed context.
8. Prefer the selected context's `wiki/` over its `raw/` for orientation, navigation, and cross-source context.
9. Treat approved `raw/` surfaces as the source of truth for source details if authored layers and raw disagree, unless the selected `SOUL.md` explicitly sets intent.
10. If approved source surfaces were refreshed, or `wiki/` is missing or stale, run `node scripts/compile-wiki.mjs` from the active context root when that script exists.
11. Commit work in the repo that owns the selected context. Do not mix parent-context commits with nested-context commits.
12. `wiki/sources/` and `wiki/manifests/` are generated outputs inside whichever context repo is active.
13. After changing repo structure, source policy, or knowledge-layer docs, run a manual consistency pass across the selected context's `README.md`, `AGENTS.md`, `SOUL.md`, `ARCHITECTURE.md`, and relevant `wiki` entry pages, then correct any drift.

# Source Policy

Replace this section with the approved source surfaces for the specific context.

Typical source categories:

- `raw/websites/<site>/public/`
- `raw/documents/<name>/sections/`
- `raw/youtube-transcripts/<channel>/*-cleaned.txt`
- `raw/manual/*.md`
- `raw/projects/<repo>/<approved-surface>`

Until this file is customized, no raw surfaces should be treated as approved by default.
