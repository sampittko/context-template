# Knowledge Base Architecture

This file explains the reusable structure of a context repo.

## Goal

Build an LLM-friendly knowledge base that:

1. ingests approved source material into `raw/`
2. compiles or authors reusable knowledge in `wiki/`
3. produces deliverables into `artifacts/`
4. optionally hosts narrower contexts under `contexts/`

## Layer Model

- `SOUL.md`: highest-authority durable intent for this context
- `raw/`: approved source evidence
- `raw/README.md`: default source-bucket semantics
- `wiki/sources/`: compiled source navigation
- `wiki/concepts/`: relatively stable patterns and principles
- `wiki/derived/`: maps, timelines, boards, open questions, and reusable working docs for understanding
- `artifacts/`: produced assets such as docs, prompts, specs, skills, and project outputs
- `artifacts/README.md`: default output-bucket semantics

## Important Boundary

Not every produced file belongs in `raw/`.

- `raw/` is for input evidence
- `wiki/` is for knowledge and synthesis
- `artifacts/` is for outputs produced by this context

If an artifact later becomes a canonical input for future reasoning, promote it explicitly into `raw/`.

## Composable Contexts

A context repo can also host nested subcontexts under `contexts/<name>/`.

A nested context can reuse the same broad scaffold:

- `SOUL.md`
- `raw/`
- `scripts/`
- `wiki/`
- `artifacts/`

Nested contexts can share some source material with the parent context, but their synthesis remains local.

## Compiler

This template includes the folder shape for `wiki/sources/` and `wiki/manifests/`.

Add a local compiler under `scripts/` only when the context actually needs one.
Generated files should not be edited by hand when a compiler exists.
