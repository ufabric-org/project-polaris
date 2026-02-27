# Custom uFabric Skills (maintained in Polaris)

Polaris contains custom uFabric skills under the repository root `skills/` folder.

Projects that want these skills should **vendor** them by copying from Polaris and syncing regularly (see `docs/project/skills/README.md`).

## What lives in `skills/`

- Each skill is a folder containing a `SKILL.md`.
- Skill folders SHOULD be stable and named with a clear prefix (for example `ufabric-...`) to avoid collisions.

## Vendored third-party skills

Polaris also contains selected vendored third-party skills under:

- `skills/vendor/`

These are curated, license-preserving, and security-reviewed copies that are standardized to be LLM-vendor agnostic.

See:

- `docs/project/skills/vendor-registry.md`

## Legacy prompts

Polaris no longer maintains a prompt library. The authoritative reusable workflows are the skills under `skills/`.
