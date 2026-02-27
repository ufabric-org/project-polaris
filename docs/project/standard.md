# uFabric Repository Standard (Polaris)

This document is the single entry point for aligning any uFabric repository to the definitions and conventions maintained in `ufabric-org/project-polaris`.

Polaris is the upstream source of truth for cross-project conventions. Repositories should adopt these standards while keeping project-specific requirements local.

## 1) Required files and conventions

### 1.1 `AGENTS.md` at repo root (required)

Every uFabric repository MUST include `AGENTS.md` at the repository root (per https://agents.md/).

Use the Polaris template as a starting point:

- `docs/project/templates/tpl-agents.md`

### 1.2 English-first (required)

Files, folders, and long-lived documentation MUST be in English unless an explicit exception is documented.

Source:

- `docs/project/language-guidelines.md`

### 1.3 AI usage rules (required)

AI outputs must be verifiable, must not fabricate facts, and must not leak secrets.

Source:

- `docs/project/ai-guidelines.md`

### 1.4 Repository structure + upstream-managed copies (required)

If you copy files from Polaris as exact copies, treat them as upstream-managed:

- Do not edit them locally.
- Change them in Polaris first.
- Then re-copy/sync them downstream.

Source:

- `docs/project/folder-structure-and-files-guidelines.md`

## 2) Skills are the standard reuse mechanism

Reusable agent workflows MUST be packaged as Skills (https://skills.sh/docs).

- Do not create/maintain a prompt library in downstream repos.
- Do not use `npx` or installers for skills. Installation is vendoring (copy + sync).
- Skills MUST be English-only and LLM-vendor agnostic.
- Third-party skills MUST have explicit licenses and must pass a prompt-injection / unsafe-instruction review before being vendored.

Source:

- `docs/project/skills/standard.md`

## 3) How to adopt (downstream SOP)

Follow the standard operating procedure:

- `docs/project/skills/downstream-adoption.md`

Minimum downstream deliverables:

1) `AGENTS.md` at repo root (adapted from the Polaris template).
2) Vendored skills copied into your agent directory:
   - Codex: `./.agents/skills/`
   - Antigravity: `./.agent/skills/`
   - Claude Code: `./.claude/skills/` (add `CLAUDE.md` only if needed)
3) A small pin file at the repo root, for example `POLARIS_REVISION`, recording:
   - the Polaris commit SHA/tag used
   - the date copied
   - the list of vendored skills

## 4) What to do when you need changes

If something should be shared across multiple repos:

1) Update Polaris first.
2) Refresh derived artifacts in Polaris if applicable (`agentic/`).
3) Sync downstream repos by re-copying the upstream-managed files/skills.

