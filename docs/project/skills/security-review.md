# Skill Security Review (Prompt Injection & Unsafe Instructions)

This checklist applies to any third-party skill content that Polaris vendors under `skills/vendor/`.

## What we are defending against

- **Instruction hijacking / prompt injection**
  - Examples: “ignore previous instructions”, “override system prompt”, “reveal hidden instructions”.
- **Secret exfiltration**
  - Examples: “read ~/.ssh”, “print API keys”, “upload tokens”, “send to a webhook”.
- **Destructive defaults**
  - Examples: “rm -rf …”, wiping files, irreversible changes without explicit user request.
- **Untrusted code execution**
  - Examples: `curl ... | sh`, downloading and running scripts without verification.

## Mandatory review steps

1) **Read the vendored `SKILL.md` end-to-end.**
2) **Scan for red-flag strings** (case-insensitive):
   - “ignore previous instructions”
   - “reveal system prompt”
   - “exfiltrate”
   - “send to”, “upload to”, “webhook”
   - `~/.ssh`, `id_rsa`, `*.pem`
   - `curl | sh`
   - `rm -rf`
3) **Check for hidden/instruction blocks**
   - HTML comments, base64 blobs, or “copy/paste this whole block” with suspicious content.
4) **Check tool assumptions**
   - If a skill assumes a specific proprietary tool, either remove that assumption or reject the import.
5) **Record results**
   - Update `UPSTREAM.md` with review date and findings.

## Suggested local scan command

From repo root:

- `rg -n \"ignore (all|any|previous) instructions|system prompt|exfiltrat|curl .*\\| *sh|rm -rf|~/.ssh|id_rsa|OPENAI_API_KEY|GITHUB_TOKEN\" skills/vendor`

## Non-negotiables

- Do not vendor third-party skills without an explicit license.
- If a skill contains unsafe instructions, either remove the unsafe parts (and document modifications) or do not vendor it.

