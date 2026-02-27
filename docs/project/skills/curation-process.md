# Skill Curation Process (Polaris as upstream)

This document defines how Polaris maintainers should discover, import, review, and keep third-party skills up to date.

Polaris uses **vendoring** (copy + sync) as the only supported installation mechanism. Do not use `npx` or other installers.

## Discovery

Use skills directories/search portals (for example https://skills.sh/) to find candidate skills.

If you want a “skill that finds skills”, use the public skill:

- https://skills.sh/vercel-labs/skills/find-skills

## Selection criteria

Prefer skills that are:

- Relevant to uFabric’s stack and goals (Python, Django, FastAPI, MkDocs/Docs).
- Maintained and widely used (recent commits, clear ownership).
- Explicitly licensed (MIT/Apache-2.0/BSD; avoid “no license”).
- LLM-vendor agnostic (or easy to make agnostic without changing intent).
- Safe by default (no destructive commands, no secret exfiltration instructions).

Reject skills that:

- Have no license or have non-redistributable terms.
- Instruct instruction hijacking (“ignore previous instructions”), secret exfiltration, or unsafe actions by default.
- Depend on a specific proprietary toolchain unless that toolchain is a deliberate uFabric dependency.

## Import procedure (vendoring)

1) **Clone upstream to a temporary location**
   - Example: clone to `/tmp/<repo-name>` and record the commit SHA.

2) **Copy the skill directory into Polaris**
   - Target location:
     - `skills/vendor/<upstream-repo-name>/<skill-dir>/`

3) **Preserve licensing**
   - Copy the upstream license text into:
     - `skills/vendor/<upstream-repo-name>/LICENSE.txt`

4) **Add sync metadata**
   - Add `UPSTREAM.md` inside each vendored skill directory:
     - upstream URL + commit SHA/tag
     - license reference
     - import date
     - local modifications summary

5) **Standardize and de-vendor**
   - Update the vendored `SKILL.md` to follow:
     - `docs/project/skills/skill-authoring-standard.md`
   - Remove assumptions about specific model vendors/tools (no “Claude/Codex/ChatGPT”).

6) **Security review**
   - Follow `docs/project/skills/security-review.md`.
   - Record “Reviewed” + findings in `UPSTREAM.md`.

7) **Register the skill**
   - Update `docs/project/skills/vendor-registry.md`.

## Sync cadence

Recommended:

- Review new upstream candidates monthly.
- Re-sync vendored skills at least quarterly, or sooner when a skill is critical to multiple repos.

## Updating an already-vendored skill

When syncing:

1) Re-clone upstream and re-copy the skill directory.
2) Re-apply Polaris standardization changes (keep diffs minimal).
3) Update `UPSTREAM.md` with the new upstream revision and re-run security review checks.
4) Ensure downstream repos can pin the updated Polaris revision.

