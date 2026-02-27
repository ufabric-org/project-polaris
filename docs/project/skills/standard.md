# uFabric Skills Standard (Polaris)

This document is the single “entry point” for aligning repositories to the uFabric Skills standard.

It covers:

- `AGENTS.md` as the agent entry point (https://agents.md/)
- Skills (https://skills.sh/docs) as the standard reuse mechanism (replacing legacy prompt files)
- Vendoring (copy + sync) as the only supported installation method
- Curation/import rules for third-party skills (including security review)

## 1) Required repository conventions

### 1.1 `AGENTS.md` at repo root

Every uFabric repository MUST include `AGENTS.md` at the repository root as the first file an agent reads.

Use Polaris template as a starting point:

- `docs/project/templates/tpl-agents.md`

### 1.2 Skills are the reuse mechanism (not prompt files)

Reusable agent behaviors MUST be packaged as skills (folders containing `SKILL.md`) rather than “prompt libraries”.

See:

- `docs/project/skills/README.md`
- `docs/project/skills/skill-authoring-standard.md`

## 2) Installation is vendoring (copy + sync)

Do not use `npx` or any other installer to “install” skills.

Instead:

1) Copy the skill folder(s) into your repo’s agent directory.
2) Treat them as **upstream-managed**.
3) Sync them regularly from Polaris.

Common agent directories:

- Codex: `./.agents/skills/`
- Antigravity: `./.agent/skills/`
- Claude Code: `./.claude/skills/`

## 3) LLM-vendor agnostic skills

Skills stored in Polaris MUST be written to work with any LLM vendor/toolchain.

- Avoid mentioning specific model vendors/tools (“Claude/Codex/ChatGPT”).
- Avoid assuming specific slash commands or UI features.
- Prefer generic language (“the assistant/agent/model”).

## 4) Third-party skills (curation + security)

Polaris may vendor a small set of third-party skills under `skills/vendor/`.

Rules:

- Only vendor skills with explicit licenses compatible with redistribution.
- Run a prompt-injection / unsafe-instruction review before importing.
- Record attribution, license, and revision in `UPSTREAM.md`.

See:

- Curation SOP: `docs/project/skills/curation-process.md`
- Security checklist: `docs/project/skills/security-review.md`
- Registry: `docs/project/skills/vendor-registry.md`

## 5) Downstream adoption SOP

See:

- `docs/project/skills/downstream-adoption.md`

## 6) Prompt for other repositories (copy/paste)

Replace `<POLARIS_SHA>` with a pinned Polaris commit SHA:

```
You are updating this repository to align with the uFabric Skills standard.

Read and follow:
https://raw.githubusercontent.com/ufabric-org/project-polaris/<POLARIS_SHA>/docs/project/skills/standard.md

Constraints:
- Follow the standard exactly.
- Do NOT use npx or any installer for skills. Installation is vendoring (copy + sync).
- Skills must be English-only and LLM-vendor agnostic.
- If you vendor third-party skills, verify licensing and run a prompt-injection safety review.

Deliverables:
- Add/update root AGENTS.md (based on the Polaris template) and ensure it points to sources of truth.
- Replace legacy prompt files with skills where applicable.
- Vendor the selected skills into the appropriate agent directory and record the pinned Polaris revision (e.g., POLARIS_REVISION).
- Document what changed and how to sync in the future.
```

