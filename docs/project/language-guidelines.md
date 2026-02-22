# Language Guidelines

These guidelines define the language, terminology, and writing standards for uFabric and all uFabric-related repositories.

## Core principles

- **Default language:** Write in plain English by default.
- **Professional tone:** Use a consistently professional and academic register.
- **Human-oriented documents:** Optimize for clarity, learnability, and long-term maintenance by humans.
- **Terminology stability:** Prefer established, canonical technical terms; avoid inventing synonyms.

## English-first policy

- **English is the source of truth.** Technical concepts, canonical names, and project terminology are defined in English.
- **Files and folders must be named in English.** Do not translate repository paths, filenames, or directory names.

## Translation rules (when a document is translated)

Translations are welcome when they increase accessibility, but they must preserve technical precision and traceability.

- **Do not translate canonical acronyms or names.** Keep standardized or project-established acronyms and their expansions in English (e.g., ADR, RFC, API, CLI, Kubernetes, GitHub Actions).
- **Do not translate code-adjacent text.** Keep code blocks, identifiers, CLI flags, configuration keys, file paths, error messages, log lines, and protocol names unchanged.
- **You may translate general explanations.** Explanatory prose may be translated as long as the canonical English term remains present.
- **Recommended pattern:** On first use, keep the English term and optionally add the translation after it.
  - Example: `Architectural Decision Record (ADR)` — *Registro de Decisión Arquitectónica* (translation for explanation only).
- **Glossary-driven consistency:** When a project glossary exists, follow it strictly and avoid alternative translations for the same term.

## Writing style and structure

- **Prefer clear sentences over complex ones.** Avoid idioms, slang, humor, or culturally-specific references.
- **Be precise and verifiable.** Make claims testable; avoid vague wording such as “obviously”, “simply”, or “it is clear that”.
- **Define terms on first use.** Expand acronyms once, then use the acronym consistently.
- **Use consistent normative language.** Prefer “MUST”, “SHOULD”, and “MAY” for requirements, recommendations, and optional behavior.
- **Use stable formats.** Prefer ISO 8601 dates (`YYYY-MM-DD`) and SI units; specify time zones when relevant.
- **Audience-appropriate depth.** For public-facing documents intended for a general audience, the prose MAY be more expansive and narrative (a coherent “story” a non-technical reader can follow and stay engaged with), while remaining sufficiently formal and precise for expert or academic readers.

## Human documents (source of truth)

Human-oriented documents include guidelines, ADRs, architecture docs, research notes, and policies.

- **Humans are the primary audience.** Write so a new contributor can understand the intent, constraints, and rationale.
- **Decisions require rationale.** When documenting decisions, include context, alternatives considered, and trade-offs.
- **Prefer durable knowledge.** Avoid time-sensitive statements when possible; when necessary, include explicit dates and versions.

## Agentic / LLM documents (derived artifacts)

Agentic documents include prompts, agent runbooks, generated summaries, automated reports, and other AI-assisted artifacts.

- **Human documents are the source of truth.** Agentic/LLM documents MUST be derived from, and consistent with, the human-maintained documentation.
- **No new policy by default.** Agentic outputs MUST NOT introduce new rules, definitions, or commitments unless a human source explicitly states them.
- **Traceability is required.** Include references to the human sources used (file paths, section titles, and, when possible, commit hashes or versions).
- **Separate facts from assumptions.** Clearly label assumptions, unknowns, and recommended follow-up actions for human review.
- **Prefer reproducibility.** When describing procedures, include exact commands, inputs/outputs, and acceptance criteria.

## Quick checklist (before merging documentation)

- Written in plain English (or an approved translation with English canonical terms preserved).
- Consistent use of acronyms, capitalization, and project terminology.
- Technical identifiers and code-adjacent text are not translated.
- Clear structure (headings, short paragraphs, and scannable lists where appropriate).
- Agentic/LLM docs cite the human sources of truth and do not add new policy.
