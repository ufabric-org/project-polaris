# Repository Map (uFabric Polaris)

This map is a navigation aid for agents and humans. It is intentionally high-level and should remain stable over time.

## Top-level directories

- `docs/`: human-maintained documentation for project-wide guidelines and templates.
- `agentic/`: agent-facing derived artifacts (runbook, indexes, and change-detection metadata).

## Key entry points

- Project overview: `README.md`
- Agent instructions: `AGENTS.md`
- Claude Code entry point: `CLAUDE.md` (if using Claude Code)
- Project documentation index: `docs/README.md`
- Project guidelines index: `docs/project/README.md`
- Skills standard (canonical): `docs/project/skills/standard.md`
- Skills overview: `docs/project/skills/README.md`
- Skills downstream adoption: `docs/project/skills/downstream-adoption.md`
- Skills (uFabric + vendored): `skills/`
  - uFabric skills: `skills/ufabric-*/`
  - Vendored third-party skills: `skills/vendor/`
- Documentation templates: `docs/project/templates/`

## Common lookups (rules)

- AI usage: `docs/project/ai-guidelines.md`
- Language and terminology: `docs/project/language-guidelines.md`
- Source code conventions: `docs/project/source-code-guidelines.md`
- Standard folder/file structure: `docs/project/folder-structure-and-files-guidelines.md`
- Default tech choices: `docs/project/technical-guidelines.md`

## Sources

- `docs/project/README.md` (guideline entry points)
- `docs/project/language-guidelines.md` (agentic document traceability expectations)
