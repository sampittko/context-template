# Artifacts

`artifacts/` stores outputs produced by this context.

Suggested buckets:

- `artifacts/docs/`: generated or authored deliverable docs
- `artifacts/projects/`: project briefs, specs, or output packages
- `artifacts/prompts/`: reusable prompts and workflows
- `artifacts/skills/`: context-produced skills or skill packs

Rule:

- `artifacts/` is not source evidence by default.
- If an artifact later becomes canonical input, promote it explicitly into `raw/`.
