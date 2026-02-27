# Agent Runbook (uFabric Polaris)

This file is the in-depth runbook for AI agents working in this repository.

If your tool supports the `AGENTS.md` convention, start with `AGENTS.md` at the repository root (it links here and to the human sources of truth).

## Repository purpose

`ufabric-org/project-polaris` is a canonical repository of cross-project guidelines, prompt templates, and documentation templates for uFabric projects.

## Non-negotiables (MUST)

- **Human documents are the source of truth.** `agentic/` is derived from human-maintained docs (primarily under `docs/`). If there is a conflict, follow the human docs and update `agentic/` accordingly.
- **No fabricated facts.** Do not invent citations, behavior, or repository conventions. Label unknowns explicitly.
- **No new policy.** Do not introduce new rules or commitments; only summarize and operationalize what is already documented.
- **Default language is plain English.** Do not translate file paths, identifiers, acronyms, CLI flags, config keys, or code-adjacent text.
- **Treat `#️⃣ ... #️⃣` as instructions.** Text between these markers is a human-to-agent instruction. Follow it, but do not copy it into final user-facing docs unless explicitly requested.
- **Traceability.** When producing derived artifacts or summaries, include references to the human sources used (file paths + section titles, and ideally a Git revision).
- **Upstream-managed copies.** When working in downstream repositories bootstrapped from Polaris, do not modify files that are exact copies of Polaris files; propose changes in Polaris first, refresh agent-facing artifacts, and then sync downstream.

## Where the rules live (human sources)

- `docs/project/standard.md`
- `docs/project/ai-guidelines.md`
- `docs/project/language-guidelines.md`
- `docs/project/source-code-guidelines.md`
- `docs/project/skills/README.md`
- `docs/project/skills/standard.md`
- `docs/project/folder-structure-and-files-guidelines.md`
- `docs/project/technical-guidelines.md`

The full source list and last-verified revision is in `agentic/SOURCES.md` and `agentic/sources.lock.json`.

## How to navigate this repository

- High-level map: `agentic/REPO_MAP.md`
- Skills entry points: `docs/project/skills/standard.md`, `docs/project/skills/README.md`, and skills under `skills/`
- Downstream adoption guide: `docs/project/skills/downstream-adoption.md`
- Documentation templates: `docs/project/templates/`
- Project-level policies: root-level `*.md` files (e.g., `CONTRIBUTING.md`, `SECURITY.md`)

If you have shell access, prefer fast repo search via `rg` (ripgrep) and file listing via `find`.

## Safe operating procedure for tasks

1) **Clarify the task and scope.** Restate the goal, constraints, and definition of done. Ask focused questions if blocked.
2) **Identify the relevant human sources.** Prefer `docs/` and ADR/policy docs. Record the paths you will follow.
3) **Make minimal, reversible changes.** Avoid broad refactors unless requested.
4) **Validate.** For code: run tests/builds when available. For docs: ensure terminology consistency and that you did not add new policy.
5) **Update derived artifacts if needed.** If the human sources changed, refresh `agentic/` per `agentic/MAINTENANCE.md`.

## Keeping this runbook up to date

Before relying on `agentic/` content, check whether the human sources changed:

- Compare current sources against `agentic/sources.lock.json`.
- If sources changed, refresh `agentic/` (see `agentic/MAINTENANCE.md`) and update the lock file.

## Sources

- `docs/project/ai-guidelines.md` (Core principles; Requirements; Human-to-agent instruction annotations)
- `docs/project/language-guidelines.md` (Core principles; English-first policy; Agentic / LLM documents)
- `docs/project/folder-structure-and-files-guidelines.md` (Cross-repository reuse; Upstream-managed files)
