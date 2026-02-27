# External Skills (Curated Sources)

This page is a curated index of external sources/catalogs a uFabric project MAY consult.

For uFabric projects, the preferred workflow is to **vendor** skills (copy them into the repo) and keep them synchronized.

Polaris may also vendor a small set of third-party skills under `skills/vendor/` with explicit license + security review.

## Recommended starting points

| Package | Notes |
| --- | --- |
| `https://github.com/vercel-labs/agent-skills` | Large catalog of general-purpose skills. |
| `https://github.com/openai/skills` | Skills tailored for Codex. |

## Curation rules (for maintainers)

- Prefer widely used, well-maintained sources.
- Prefer skills that are agent/tool-agnostic when possible.
- Document why a skill is recommended and any caveats (security, cost, network access).
- If vendoring third-party skills, preserve licensing requirements and attribution.
- Only vendor third-party skill content in Polaris when licensing and maintenance ownership are explicit.
