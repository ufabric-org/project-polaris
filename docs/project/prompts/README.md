# Prompt Library

This directory contains reusable prompts for uFabric projects. Prompts are **agentic/LLM documents** and MUST follow the uFabric language and documentation rules.

This prompt library is tailored for uFabric projects and uses `ufabric-org/project-polaris` as the canonical reference for cross-project guidelines, rules, and templates.

## Entry points

- Task prompts (direct-use): `tasks.md`
- Template prompts (adapt and extend): `templates.md`

## How to use these prompts

1. Pick a task prompt or a template prompt.
2. Copy the **Prompt (copy/paste)** block into your LLM tool.
3. Replace placeholders (e.g., `<TASK>`, `<FILES>`, `<CONSTRAINTS>`).
4. Provide relevant **human source-of-truth** documents (project docs, ADRs, policies) and repository context.
5. Before running a prompt, ensure that relevant artifacts are backed up in GitHub. This is a recommendation, not a constraint.
6. Review the output critically. A human is responsible for validation and final decisions.

## Prompt design rules (for adding or editing prompts)

- **Human source of truth:** Prompts MUST be based on, and remain consistent with, human-maintained documentation.
- **No new policy:** Prompts MUST NOT introduce new rules or commitments unless they are already stated in human documents.
- **Explicit inputs/outputs:** Specify required inputs, constraints, and an unambiguous output format.
- **Traceability:** Require references to the human documents used (file paths, section titles, and ideally a commit hash or version).
- **Assumptions control:** Require the model to separate facts from assumptions and to ask questions when blocked.
- **Operational safety:** Prefer minimal changes, reversible steps, and clear validation (tests, checks, acceptance criteria).
- **Plain English and professional tone:** Keep prompts readable and maintainable by humans.
- **Stable placeholders:** Use consistent, clearly delimited placeholders like `<PLACEHOLDER_NAME>`.
- **Naming convention:** Task prompts MUST start with `task-` and templates MUST start with `template-`.
- **Collaborative creation:** New prompts MUST be created in collaboration with maintainers. Start by asking what the prompt should do, the expected inputs/outputs, and any constraints.
- **Polaris reference:** For uFabric projects, prompts SHOULD reference Polaris documents when defining guidelines, rules, or common structures (prefer raw GitHub URLs for cross-repository reuse).
- **Upstream-first for shared prompts:** If a prompt is likely to be useful across multiple uFabric repositories, create/update it in Polaris first and then sync or reference it from downstream repositories. Downstream repositories MAY create project-specific prompts, but they SHOULD NOT edit prompts that are exact copies of Polaris prompts.

## Linking guidance (cross-repository reuse)

When prompts are used from other repositories, relative links may not resolve. Prefer linking to the canonical source in Polaris using a pinned ref:

- Recommended: use a tag or commit SHA (stable over time).
- Acceptable: use `main` (convenient, but may change).

Example:

- Pattern (pinned): `https://raw.githubusercontent.com/ufabric-org/project-polaris/<TAG_OR_COMMIT_SHA>/docs/project/language-guidelines.md`
- Convenience (branch): [Language guidelines (raw, main)](https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/docs/project/language-guidelines.md)
