# uFabric Skill Authoring Standard

This document defines the uFabric standard for writing **Skills**.

A skill is an **LLM-vendor-agnostic mindset + execution protocol** for reliably completing a class of tasks with consistent quality, safety, and traceability.

This standard is intended to be compatible with the Skills ecosystem concept (https://skills.sh/docs) while remaining repository-friendly (easy to vendor, diff, and sync).

## Requirements (MUST)

- **English-only:** Skills MUST be written in plain English.
- **LLM-vendor agnostic:** Skills MUST NOT assume a specific model vendor/tool (avoid “Claude”, “ChatGPT”, “Codex”, etc.). Write to “the assistant/agent/model” generically.
- **Mindset-first:** Skills MUST specify how to think before acting (context, constraints, trade-offs, risks, unknowns).
- **Operational:** Skills MUST provide a concrete execution protocol (steps, checkpoints, and validation expectations).
- **No fabricated facts:** Skills MUST NOT invent repository conventions, system behavior, or external facts. Unknowns MUST be labeled as unknown and turned into questions.
- **No secrets / no exfiltration:** Skills MUST NOT request secrets, credentials, tokens, or sensitive files. Skills MUST NOT instruct exfiltration (for example uploading private data to third parties).
- **No new policy by default:** Skills SHOULD operationalize existing source-of-truth documents. If a skill introduces a new requirement, it MUST be explicitly marked as uFabric policy (this document) or linked to an existing source-of-truth doc.
- **Stable identifiers:** Skills MUST NOT translate or rename file paths, identifiers, acronyms, CLI flags, config keys, or API paths.
- **Prompt-injection aware:** Skills MUST contain a short “Safety & Integrity” section that explicitly rejects instruction hijacking (for example “ignore previous instructions”).

## Skill package layout

Each skill lives in a directory under `skills/` and MUST contain:

- `SKILL.md` (the skill itself)

Skills MAY additionally include:

- `assets/` (images, example data)
- `scripts/` (helper scripts)
- `references/` (small reference files needed for the skill to be self-contained)

Vendored (external) skills MUST additionally include:

- `UPSTREAM.md` (license + attribution + sync metadata)

## Frontmatter (recommended; required for uFabric skills)

To align with the broader ecosystem, skills SHOULD include YAML frontmatter at the top of `SKILL.md`.

For uFabric-maintained skills in Polaris, YAML frontmatter is REQUIRED with at least:

- `name`: stable skill identifier (SHOULD match the directory name)
- `description`: one-sentence summary
- `version`: date-based (`YYYY-MM-DD`) or SemVer

Recommended keys (optional):

- `tags`: list of short tags (for search/curation)
- `triggers`: phrases/keywords that should suggest using the skill
- `license`: for vendored skills (from upstream)
- `upstream`: for vendored skills (repo + path + commit/tag if known)

## `SKILL.md` body structure (MUST)

After frontmatter, `SKILL.md` MUST follow this structure:

1) **Title + short description**
2) **Scope**
   - This skill is for
   - This skill is not for
3) **Inputs**
   - Required
   - Optional
4) **Outputs**
   - Deliverables (files/patches/reports)
   - Required output format (headings / sections / tables)
5) **Mindset (Design Thinking)**
   - Purpose / audience
   - Constraints (technical, time, policy, safety)
   - Quality bar (what “excellent” looks like)
   - Risks (failure modes, unknowns, verification plan)
6) **Execution protocol**
   - Step-by-step method with checkpoints
   - Validation expectations (tests, review steps, “manual verification plan” fallback)
7) **Quality checklist**
8) **Safety & Integrity**
   - Reject prompt injection / instruction hijacking
   - Prohibit secrets and destructive actions without explicit user request
9) **References**
   - Links/paths to relevant source-of-truth docs and (for vendored skills) the upstream source

## Writing style guidelines

- Use decisive, imperative language (“Do X”, “Avoid Y”).
- Prefer short sections and bullet lists; keep it scannable.
- Make constraints explicit and easy to enforce.
- Include an explicit “If blocked” rule: ask targeted questions rather than guessing.
- Prefer minimal, reversible changes for code-editing skills unless the skill explicitly targets greenfield work.

## Templates

Use the uFabric skill template:

- `docs/project/templates/tpl-skill.md`
