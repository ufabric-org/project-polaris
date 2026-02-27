# Agent Instructions

This file provides instructions for AI agents and coding assistants working in this repository.
It follows the `AGENTS.md` convention described at https://agents.md/.

## Start here

- Project overview: `README.md`
- Architecture / docs: `docs/`
- Code: `src/` (or the primary code directory in this repo)
- Skills (if used): `skills/` and project-installed agent skills (for example `./.agents/skills/`, `./.claude/skills/`)

## Quick commands

Replace these with the real commands for your repo:

- Install: `<your install command>`
- Build: `<your build command>`
- Test: `<your test command>`
- Lint/format: `<your lint/format command>`

## Conventions (repo-specific)

- Language: plain English for documentation; do not translate code identifiers, file paths, or config keys.
- Scope: keep changes minimal and avoid unrelated refactors.
- Safety: never introduce secrets; avoid destructive operations unless explicitly requested.

## Repository map (high level)

- `docs/`: documentation, ADRs, and templates
- `src/`: application/source code (if present)
- `tests/`: test suites (if present)

## Derived agent artifacts (optional)

If this repo maintains derived agent-facing docs (for example under `agentic/`), keep them in sync with the human sources of truth and document the refresh procedure.
