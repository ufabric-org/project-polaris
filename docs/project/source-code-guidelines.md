# Source Code Guidelines

These guidelines define naming and commenting conventions for source code in uFabric projects.

They complement the uFabric language guidelines and are intended to improve readability, reviewability, and long-term maintainability.

## Naming

- **Follow language conventions.** Use the language’s community-standard style guide for naming (for example, PEP 8 for Python). When a project defines stricter rules, the project rules take precedence.
- **Use English identifiers.** Variable names, function names, class names, and other identifiers SHOULD be English words or established technical terms.
- **Use canonical acronyms consistently.** When acronyms are used, keep them stable and consistent (for example, `API`, `HTTP`, `ADR`). Do not invent new abbreviations without a clear need.

## Comments and docstrings

- **Comments MUST follow the language guidelines.** They must be written in plain English with a professional tone.
- **Be concise.** Comments MUST NOT be verbose and SHOULD be included only when needed to reduce ambiguity.
- **Prefer “why” over “what”.** Avoid restating code that is already clear from names and structure. Document rationale, constraints, and non-obvious behavior.
- **Do not document standard conventions.** Do not add explanatory comments for well-known framework- or language-conventional files and patterns when the intent is already widely understood (for example, do not explain a standard `urls.py` in a typical Django project).
- **Document complex logic and impactful decisions.** Add or keep comments when they clarify:
  - tricky algorithms or edge cases
  - important trade-offs
  - security, safety, or reliability constraints
  - non-obvious performance considerations

