# Rules Index (Derived)

This file is a short index of “what to follow” when working in this repository. It does not replace the human source documents.

## Language and documentation

- Write in plain English by default; use a professional, academic tone.
  - Source: `docs/project/language-guidelines.md` → “Core principles”, “Writing style and structure”
- English is the source of truth; files and folders must be named in English.
  - Source: `docs/project/language-guidelines.md` → “English-first policy”
- For agentic/LLM documents: human docs are the source of truth; no new policy; traceability; separate facts from assumptions.
  - Source: `docs/project/language-guidelines.md` → “Agentic / LLM documents (derived artifacts)”

## AI usage and safety

- Humans are accountable; AI outputs must be validated before becoming source of truth.
  - Source: `docs/project/ai-guidelines.md` → “Core principles”, “Requirements (MUST)”
- Do not fabricate facts/citations; label unknowns.
  - Source: `docs/project/ai-guidelines.md` → “Requirements (MUST)”
- Do not expose secrets or sensitive data to unapproved tools.
  - Source: `docs/project/ai-guidelines.md` → “Requirements (MUST)”
- Treat `#️⃣ ... #️⃣` markers as human-to-agent instructions; follow them and do not include the instruction text in final user-facing output unless asked.
  - Source: `docs/project/ai-guidelines.md` → “Human-to-agent instruction annotations”

## Prompt authoring (for `docs/project/prompts/`)

- Prompts must be based on human-maintained documentation; do not introduce new policy; include explicit inputs/outputs and traceability.
  - Source: `docs/project/prompts/README.md` → “Prompt design rules (for adding or editing prompts)”
- Naming convention: task prompts start with `task-` and templates start with `template-`.
  - Source: `docs/project/prompts/README.md` → “Prompt design rules (for adding or editing prompts)”

## Repository structure expectations

- Prefer using the shared folder and file structure guidelines; add only what is needed and document rationale.
  - Source: `docs/project/folder-structure-and-files-guidelines.md` → “Common”

## Cross-repository reuse (Polaris as upstream)

- If a file is an exact copy from Polaris, treat it as upstream-managed: do not modify it downstream; change it in Polaris first and then sync.
  - Source: `docs/project/folder-structure-and-files-guidelines.md` → “Cross-repository reuse (Polaris as upstream)”
- For prompts: create/update shared prompts in Polaris first; downstream repositories may add project-specific prompts but should not edit copied Polaris prompts.
  - Source: `docs/project/prompts/README.md` → “Prompt design rules (for adding or editing prompts)”

## Sources

- `docs/project/ai-guidelines.md`
- `docs/project/language-guidelines.md`
- `docs/project/folder-structure-and-files-guidelines.md`
- `docs/project/prompts/README.md`
