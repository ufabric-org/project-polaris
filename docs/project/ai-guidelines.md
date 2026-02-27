# AI Guidelines

These guidelines define how uFabric projects use AI systems (LLMs and other tools) to create and maintain documentation, code, and research artifacts.

The goals are to enhance human capabilities while preserving responsibility, verifiability, sustainability, and technological sovereignty.

## Core principles

- **Human accountability:** Humans are responsible for decisions, approvals, and production changes.
- **Verifiability:** Prefer outputs that can be checked (tests, references, reproducible steps).
- **Transparency:** Make assumptions explicit; separate facts from hypotheses and proposals.
- **Data stewardship:** Do not expose secrets or sensitive data to tools that are not approved for it.
- **Sustainability:** Prefer the smallest tool/model that satisfies the task and avoid unnecessary compute.

## Requirements (MUST)

- **Human supervision:** All AI-generated content MUST be validated and supervised by a human before it becomes a source of truth or is merged.
- **No fabricated facts:** AI outputs MUST NOT invent facts, citations, measurements, or system behavior. When information is unknown, it MUST be labeled as unknown.
- **No secrets or credentials:** Never paste secrets (API keys, tokens, private keys), personal data, or confidential material into external tools unless explicitly approved.
- **License awareness:** Do not copy text or code from unknown sources. If external content is used, preserve attribution and verify license compatibility.

## Source of truth for uFabric projects

For cross-project rules, repositories MAY reference this repository (`ufabric-org/project-polaris`) as the canonical source of truth.

Key references:

- Language guidelines: https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/docs/project/language-guidelines.md
- Source code guidelines: https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/docs/project/source-code-guidelines.md
- Skills standard: https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/docs/project/skills/standard.md

## Task instruction standards (applies to skills and one-off requests)

Prefer structured task instructions that include:

- task goal and scope
- repository context and constraints
- required inputs and file paths
- definition of done and validation steps
- explicit output format

Reusable workflows live in `skills/` (and are described in `docs/project/skills/`).

## Human-to-agent instruction annotations

Projects may embed short, explicit instructions for AI agents directly inside documents. The text between the `#️⃣` markers is treated as a human instruction to the agent.

Primary use cases:

- fact-check a paragraph
- rewrite for clarity and professional tone
- expand or shorten a section (without changing meaning)
- identify ambiguous requirements
- request citations or evidence

### Recommended formats

Preferred (hidden in rendered Markdown):

```md
<!-- #️⃣fact-check this paragraph and add citations#️⃣ -->
```

Visible inline:

```md
#️⃣fact-check this paragraph and add citations#️⃣
```

Multi-line block (place the block immediately above the target content):

```md
<!-- #️⃣
Rewrite the next section to be clearer and less verbose.
Preserve meaning. Do not introduce new policy.
#️⃣ -->
```

### Agent rules

- Treat `#️⃣ ... #️⃣` as instructions, not document content.
- Do not include instruction text in final user-facing output unless explicitly asked.
- If an instruction cannot be completed safely, stop and ask focused questions.
- After completing the instruction, remove the annotation or replace it with a short resolution note only if the repository conventions allow it.

## Code-specific guidance

- Follow language-specific naming conventions (for example, PEP 8 for Python).
- Enforce professional, concise comments and docstrings. Comments should explain non-obvious rationale and complex logic, not restate standard conventions.

## Suggested validation checklist

- Identify and list assumptions and unknowns.
- For code changes: run tests/builds and report results.
- For documentation: ensure terminology and acronyms are consistent; preserve canonical English technical terms in translations.
- For research artifacts: separate evidence from hypotheses and include reproducible steps.
