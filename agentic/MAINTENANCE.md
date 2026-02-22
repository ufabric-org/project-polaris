# Agentic Maintenance (keep `agentic/` in sync)

This document defines how an agent should detect documentation changes and refresh the derived artifacts in `agentic/` without introducing new policy.

## What is “source of truth” vs “derived”

- **Source of truth:** human-maintained docs (primarily under `docs/` and project-level policy docs at the repo root).
- **Derived:** everything under `agentic/` (runbooks, indexes, summaries, and metadata).

If there is a conflict, update `agentic/` to match the human docs.

## Change detection

`agentic/sources.lock.json` is the authoritative change-detection input.

If Git is available:

1) Check whether the repo is dirty (uncommitted changes).
2) Compare current file hashes (or last commits) of the source list against the lock file.

Suggested commands (examples only):

- `git status --porcelain`
- `git rev-parse HEAD`
- `git log -n 1 --format=%H -- <path>`
- `shasum -a 256 <path>` (macOS) or `sha256sum <path>` (Linux)

If Git is not available:

- Compare file modification times and file sizes, and explicitly mark revision as “unknown”.

## Update procedure (safe and reversible)

1) Identify which source files changed (from the lock file comparison).
2) Re-read the changed human documents and note the sections that changed.
3) Regenerate the derived artifacts in `agentic/`:
   - `README.md`
   - `AGENT.md`
   - `REPO_MAP.md`
   - `RULES.md`
   - `SOURCES.md`
4) Update `agentic/sources.lock.json` (date + revisions + hashes).
5) Validate:
   - Ensure no new policy was introduced.
   - Ensure every rule summary has a citation to a human source (path + section title).
   - Ensure paths/identifiers are not translated.
6) Keep changes minimal and review diffs carefully.

## When to refresh `agentic/`

- After any change to the primary sources listed in `agentic/SOURCES.md`.
- After adding new project-level rules or policies.
- Before asking an agent to do high-impact work, if the lock file is stale.

## Sources

- `docs/project/language-guidelines.md` → “Agentic / LLM documents (derived artifacts)”
- `docs/project/ai-guidelines.md` → “Requirements (MUST)”
