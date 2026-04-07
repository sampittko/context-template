# Knowledge Base Architecture

This file explains the reusable structure of a context repo.

## Goal

Build an LLM-friendly knowledge base that:

1. ingests approved source material into `1-raw/`
2. compiles or authors reusable knowledge in `2-wiki/`
3. produces deliverables into `3-artifacts/`

## Root Hierarchy

Keep the semantic flow visually dominant at the root:

1. `1-raw/`
2. `2-wiki/`
3. `3-artifacts/`

Other root-level support directories are optional and should use a leading underscore so they do not compete with the flow.

Example:

- `_scripts/` for local tooling such as wiki compilers or refresh helpers

## Layer Model

- `SOUL.md`: highest-authority durable intent for this context
- `1-raw/`: approved source evidence
- `1-raw/README.md`: default source-bucket semantics
- `1-raw/contexts/`: imported context repos or exported context slices used as inputs
- `2-wiki/sources/`: compiled source navigation
- `2-wiki/concepts/`: relatively stable patterns and principles
- `2-wiki/derived/`: maps, timelines, boards, open questions, and reusable working docs for understanding
- `3-artifacts/`: produced assets such as docs, prompts, specs, skills, and project outputs
- `3-artifacts/README.md`: default output-bucket semantics
- `_scripts/`: optional local tooling that supports this context but is not part of the semantic layer model

## Important Boundary

Not every produced file belongs in `1-raw/`.

- `1-raw/` is for input evidence
- `2-wiki/` is for knowledge and synthesis
- `3-artifacts/` is for outputs produced by this context

If an artifact later becomes a canonical input for future reasoning, promote it explicitly into `1-raw/`.

An imported context can still live under `1-raw/contexts/` because the entire imported repo is an input surface relative to the current context.

## Imported Contexts

Use `1-raw/contexts/<name>/` when another context repo or exported context slice informs the current context.

Treat imported contexts as source material:

- read from them as inputs to the current context
- avoid authoring inside them as part of the current context's work
- keep independent child contexts as separate repos when they need their own lifecycle, commit history, or output boundaries

## Compiler

This template includes the folder shape for `2-wiki/sources/` and `2-wiki/manifests/`.

Add a local compiler under `_scripts/` only when the context actually needs one.
Generated files should not be edited by hand when a compiler exists.
Keep general tooling out of `2-wiki/` so the authored knowledge layer stays semantically clean.
