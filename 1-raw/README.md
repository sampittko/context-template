# Raw Sources

`1-raw/` stores input evidence for the current context.

Use these buckets as defaults:

- `1-raw/manual/`: notes maintained directly inside this context repo
- `1-raw/documents/`: cloned first-party document repos such as a CV or one-pager
- `1-raw/websites/`: readable exported surfaces from website repos
- `1-raw/youtube-transcripts/`: transcript repo clones, preferably using cleaned reading copies
- `1-raw/projects/`: approved readable surfaces from project repos when they are inputs to this context
- `1-raw/contexts/`: imported context repos or exported context slices when they are inputs to this context

Rule:

- If this context reads from it, it belongs in `1-raw/`.
- Imported contexts can live in `1-raw/contexts/` even when they contain their own internal `2-wiki/` or `3-artifacts/` structure elsewhere, because they are inputs relative to this context.
- If this context produces it, it belongs in `3-artifacts/` unless explicitly promoted later.
