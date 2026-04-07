# Raw Sources

`raw/` stores input evidence for the current context.

Use these buckets as defaults:

- `raw/manual/`: notes maintained directly inside this context repo
- `raw/documents/`: cloned first-party document repos such as a CV or one-pager
- `raw/websites/`: readable exported surfaces from website repos
- `raw/youtube-transcripts/`: transcript repo clones, preferably using cleaned reading copies
- `raw/projects/`: approved readable surfaces from project repos when they are inputs to this context

Rule:

- If this context reads from it, it belongs in `raw/`.
- If this context produces it, it belongs in `artifacts/` unless explicitly promoted later.
