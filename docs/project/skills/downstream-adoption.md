# Downstream Adoption Guide (uFabric Polaris)

This guide explains how other repositories should adopt uFabric standards from `ufabric-org/project-polaris`, with a focus on:

- `AGENTS.md` as the agent entry point (https://agents.md/)
- Skills as the standard reusable workflow mechanism (https://skills.sh/docs)
- Vendoring (copy + sync) instead of CLI-based installation

## Goals

- Make repository navigation consistent for humans and agents.
- Share the same reusable agent workflows across repositories.
- Keep “upstream-managed” artifacts synchronized and avoid local drift.

## What downstream repos should vendor from Polaris

Downstream repositories SHOULD vendor (copy) the following, as appropriate:

1) **Agent entry point**
   - Copy the `AGENTS.md` template: `docs/project/templates/tpl-agents.md`
   - Create the repo’s own `AGENTS.md` at the downstream repo root.

2) **Custom uFabric skills (preferred)**
   - Vendor one or more skill directories from Polaris `skills/` into the downstream repo’s agent directory:
     - Codex: `./.agents/skills/<skill-dir>/`
     - Antigravity: `./.agent/skills/<skill-dir>/`
     - Claude Code: `./.claude/skills/<skill-dir>/`

3) **Vendored third-party skills (optional)**
   - If a downstream repo wants external skills, prefer the curated+reviewed copies already vendored into Polaris under `skills/vendor/`.
   - Vendor them the same way as custom skills (copy into your agent directory).

4) **Guidelines and templates (reference, not necessarily copy)**
   - Downstream repos SHOULD link to Polaris guidelines (raw GitHub links pinned to a tag/SHA when possible).
   - Only copy documents when you intentionally want an upstream-managed exact copy (and then treat it as upstream-managed).

## Upstream-managed rule (non-negotiable)

If a downstream repository vendors a file/folder from Polaris as an upstream-managed copy:

- Do not edit it locally.
- Make changes in Polaris first.
- Then re-copy into the downstream repository.

This rule applies to vendored skills and any other upstream-managed docs.

## Standard operating procedure (SOP)

### 1) Add `AGENTS.md` to the downstream repo

At the downstream repo root:

- Create `AGENTS.md` using `docs/project/templates/tpl-agents.md` as a starting point.
- Update “Quick commands” and repo-specific conventions.
- Keep it short and operational; link to your repo’s source-of-truth docs and to vendored skills.

Do not create `AGENT.md` unless a specific toolchain requires it.

### 2) Vendor the uFabric skills you want

Pick skills from Polaris `skills/` and copy them into the appropriate directory for your agent toolchain.

Example (Codex):

- From Polaris: `skills/ufabric-code-review/`
- To downstream: `./.agents/skills/ufabric-code-review/`

### 3) Record what you copied (pinning)

Downstream repositories SHOULD record the Polaris revision they vendored from.

Recommended: create a small lock file at the downstream repo root, for example:

- `POLARIS_REVISION` containing:
  - the Polaris commit SHA (or tag)
  - the date copied
  - the list of skills vendored

### 4) Sync regularly

Downstream repositories SHOULD sync vendored skills frequently:

- On a schedule (for example weekly), and
- Whenever you upgrade important repo conventions or agent workflows

Sync process:

1) Pull latest Polaris (or pick a target tag/SHA).
2) Re-copy the vendored skills into the downstream repo.
3) Review diffs and validate any downstream workflows that depend on them.

### 5) Add external (curated) skills (optional)

If you vendor skills from external sources listed in `docs/project/skills/curated.md`:

- Copy the skill directories into your repo (same vendoring rule).
- Preserve licensing/attribution requirements.
- Record upstream revision in your `POLARIS_REVISION` or a separate lock file.
- Run a prompt-injection / unsafe-instruction review (see `docs/project/skills/security-review.md`).

## Where to find the source material in Polaris

- Agent entry point template: `docs/project/templates/tpl-agents.md`
- Skills overview: `docs/project/skills/README.md`
- Curated external skills: `docs/project/skills/curated.md`
- Custom uFabric skills: `skills/`
- Vendored third-party skills: `skills/vendor/`
- Cross-repo “upstream-managed” rule: `docs/project/folder-structure-and-files-guidelines.md`
