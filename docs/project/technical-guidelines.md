# Technical Guidelines

These guidelines define default technology choices for common uFabric project types.
They are intended to reduce decision overhead and increase consistency across repositories.

## Default stack (common tasks)

- **Static websites / documentation sites:** Use MkDocs.
- **Web apps that require a backend:** Use Django.
- **API services:** Use FastAPI.
- **Projects that need both a backend and APIs:** Use Django for the backend and FastAPI for the API layer, unless a documented decision (ADR recommended) justifies an alternative.

## Language preference

- **Python is recommended but not mandatory.** If a different language/runtime is used, document the rationale and constraints (ADR recommended).

## Official documentation (required)

- **Follow the official documentation first.** When choosing languages, frameworks, tools, libraries, and patterns, the official documentation MUST be treated as the primary reference.
- **Pin and record versions.** Repositories SHOULD record the exact versions used (runtime, framework, key tooling) in standard files (for example, `pyproject.toml`, `requirements.txt`, or `package.json`) and in human documentation when helpful.
- **Include offline documentation when possible.** Projects SHOULD include a PDF snapshot of the official documentation for each major language/framework/tool they rely on, when redistribution is permitted by the documentation’s license.

### Recommended location for documentation PDFs

Store documentation PDFs under:

- `docs/reference/official/`

Recommended naming convention:

- `{name}-{version}.pdf` (for example, `python-3.12.pdf`, `django-5.0.pdf`, `fastapi-0.110.pdf`)

Each project SHOULD include `docs/reference/official/README.md` listing:

- what PDFs are included
- source URLs
- versions and capture dates
- license/redistribution notes

## Deviations

- Deviations from the default stack MUST be explicitly documented (ADR recommended) and SHOULD include alternatives considered and trade-offs.
