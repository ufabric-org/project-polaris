# Agent Instructions (project-polaris)

This repository is uFabric’s canonical source for cross-project guidelines, prompt templates, and documentation templates.

This file follows the `AGENTS.md` convention described at https://agents.md/ so AI tools can reliably load the right context.

## Start here

- Repository overview: `README.md`
- Project guideline index: `docs/project/README.md`
- Repository standard (entry point): `docs/project/standard.md`
- Skills (standard reusable workflows): `docs/project/skills/standard.md`, `docs/project/skills/README.md`, and skills under `skills/`
- In-depth agent runbook (derived): `agentic/AGENT.md`

## Source of truth vs derived artifacts

- **Source of truth:** human-maintained documentation under `docs/` and root project policies (`*.md` at repo root).
- **Derived artifacts:** everything under `agentic/` (runbooks, indexes, and change-detection metadata).

If anything conflicts, follow the human docs and refresh `agentic/` (see `agentic/MAINTENANCE.md`).

## Non-negotiables

- Do not fabricate facts; mark unknowns explicitly.
- Do not introduce new policy; only summarize/index what is already documented.
- Keep documents in plain English (do not translate file paths, identifiers, acronyms, CLI flags, or config keys).
- Treat any text between `#️⃣ ... #️⃣` as human-to-agent instructions.

## What to do after changes

If you modify human sources (typically under `docs/`), refresh derived agent artifacts in `agentic/` per `agentic/MAINTENANCE.md`.
