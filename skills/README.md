# Skills (Polaris)

This folder contains skills for downstream projects to vendor (copy) and keep synchronized.

- `ufabric-*`: uFabric-maintained skills (preferred).
- `vendor/`: curated third-party skills vendored into Polaris with license + security review.

## How to use from downstream projects

- Copy one or more `skills/<skill-dir>/` folders into your project’s agent directory (for example `./.agents/skills/` for Codex).
- Treat copied skills as upstream-managed and sync them from Polaris regularly.

## Included skills

Custom uFabric skills (directories containing `SKILL.md`):

- `ufabric-adr-draft`
- `ufabric-agentic-folder-bootstrap`
- `ufabric-code-change-with-tests`
- `ufabric-code-review`
- `ufabric-documentation-coherence-review`
- `ufabric-documentation-review`
- `ufabric-documentation-update`
- `ufabric-language-guidelines-enforce`
- `ufabric-research-protocol`

See `docs/project/skills/custom.md` for guidance and ownership expectations.

## Vendored third-party skills

See:

- `docs/project/skills/vendor-registry.md`
