# Vendored Skills Registry (Polaris)

Polaris vendors a small number of third-party skills under `skills/vendor/` for convenience and consistency across uFabric projects.

Each vendored skill directory MUST include an `UPSTREAM.md` file with attribution, license, revision, and security review notes.

## Current vendored skills

| Skill | Why it is here | License |
| --- | --- | --- |
| `skills/vendor/jeffallan-claude-skills/fastapi-expert/` | FastAPI/Pydantic v2 implementation guidance + references (matches uFabric backend stack). | MIT |
| `skills/vendor/jeffallan-claude-skills/django-expert/` | Django/DRF implementation guidance + references (matches uFabric backend stack). | MIT |
| `skills/vendor/readthedocs-skills/readthedocs-write-config/` | `.readthedocs.yaml` v2 authoring for MkDocs/Sphinx (docs pipeline support). | MIT |
| `skills/vendor/readthedocs-skills/readthedocs-build-failure-triage/` | RTD build log triage + minimal fixes (docs reliability). | MIT |
| `skills/vendor/kesslerio-academic-deep-research/academic-deep-research/` | Rigorous research workflow with citations + checkpoints (research skill). | Apache-2.0 |

## Rejected candidates (documented)

- `jeremylongshore/claude-code-plugins-plus-skills` (license is proprietary; not suitable for vendoring/redistribution).
- `199-biotechnologies/claude-deep-research-skill` (no explicit open-source license; not suitable for vendoring/redistribution).

