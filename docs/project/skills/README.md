# Skills (Standard)

uFabric repositories use **Skills** (https://skills.sh/docs) as the standard way to package reusable agent behaviors and workflows.

Skills **replace copy/paste prompt files** as the primary reuse mechanism. A skill is a folder containing a `SKILL.md` (and optionally scripts/assets) that can be installed/configured for a specific agent toolchain.

Canonical standard document:

- `docs/project/skills/standard.md`

## Why Skills

- **Reusable and composable:** skills can be installed across repositories and shared within a team.
- **Tool-aware distribution:** the same skill can be configured for different agents (for example Codex or Claude Code).
- **Versionable and curated:** Polaris can act as an upstream skill pack, plus a curated index of external skills.

## Using skills in projects (copy + sync)

For uFabric projects, “installation” is **vendoring**: copy skills from their upstream source and keep them synchronized regularly.

Supported agents and their project directories include:

- **Codex:** `./.agents/skills/`
- **Antigravity:** `./.agent/skills/`
- **Claude Code:** `./.claude/skills/`

### Install from Polaris (custom uFabric skills)

1) Copy one or more skills from Polaris `skills/<skill-dir>/` into your project’s agent directory, for example:

- Codex: copy to `./.agents/skills/<skill-dir>/`
- Antigravity: copy to `./.agent/skills/<skill-dir>/`
- Claude Code: copy to `./.claude/skills/<skill-dir>/`

2) Treat vendored copies as **upstream-managed**:

- Do not edit vendored copies locally.
- If a change is needed, update the skill in Polaris first, then re-copy.

3) Sync regularly:

- Re-copy from Polaris on a schedule (for example weekly) and as part of major repo upgrades.
- Pin and record the upstream revision you copied from (for example the Polaris commit SHA) in your repo docs or an internal lock file.

For the downstream standard operating procedure, see:

- `docs/project/skills/downstream-adoption.md`

## Polaris as upstream

Polaris serves three purposes:

1) **Custom uFabric skills maintained here:** `skills/ufabric-*/` (preferred).
2) **Vendored third-party skills (curated + reviewed):** `skills/vendor/` (selected external skills copied into Polaris with license + security review).
3) **Curated external sources:** a short index of external catalogs projects may consult.

See:

- Curated external skills: `docs/project/skills/curated.md`
- Custom uFabric skills in Polaris: `docs/project/skills/custom.md`
- Vendored skills registry: `docs/project/skills/vendor-registry.md`

## Creating or updating a uFabric skill

- Prefer upstream-first: if a skill is useful across multiple uFabric repositories, add/update it in Polaris first.
- Keep skill docs in plain English and do not translate file paths, identifiers, or config keys.
- Do not introduce new project-wide policy inside skills; skills should operationalize existing human source-of-truth docs.
- Skills must be **LLM-vendor agnostic** (no “Claude/Codex/ChatGPT” assumptions).

Authoring standard and template:

- Standard: `docs/project/skills/skill-authoring-standard.md`
- Template: `docs/project/templates/tpl-skill.md`

Maintainer procedures:

- Curation SOP: `docs/project/skills/curation-process.md`
- Security checklist: `docs/project/skills/security-review.md`
