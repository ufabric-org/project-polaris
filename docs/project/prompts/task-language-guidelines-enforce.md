# Language Guidelines Enforcement

## Intent

Enforce the uFabric language guidelines across a repository by auditing and applying fixes to folder names, filenames, and human-facing content.

This prompt MAY rename files and folders and MAY edit file contents to align with the guidelines.

## When to use

- Before merging documentation changes.
- After reorganizing folders or renaming files.
- When adding translated documents and you want to validate terminology and acronym rules.

## Required inputs

None. This prompt audits the repository it is executed in.

Optional inputs:

- `<EXCEPTIONS>` (optional): allowed non-English proper nouns, quotes, dataset names, or external references.

## Output requirements

- A short plan before applying changes.
- A set of changes that improve language compliance without introducing new meaning.
- A final report with:
  - what changed (renames and content edits)
  - what was not changed (and why)
  - remaining issues that require human decisions

## Prompt (copy/paste)

```text
You are enforcing language compliance in a uFabric repository.

Your job is to check names and human-facing content against the uFabric guidelines and apply fixes.
You MUST NOT create new files. You MUST NOT introduce new scope, new requirements, or new factual claims.

### Language guidelines (source of truth)
Use this as the source of truth:
- https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/docs/project/language-guidelines.md

### Source code guidelines (source of truth for code comments)
Use this as the source of truth:
- https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/docs/project/source-code-guidelines.md

### Exceptions (optional)
<EXCEPTIONS>

### Hard constraints
- Do not create new files or folders.
- Do not add new sections, new topics, or new requirements to documentation.
- Do not add new product behavior, APIs, or implementation features.
- You MAY fix grammar, spelling, and phrasing to improve clarity and professionalism as long as you preserve meaning.
- You MAY rename files and folders to English names and update references accordingly.
- Do not introduce new information. Prefer rewrites over additions. If a fix would require adding new content (for example, a new paragraph or a new comment), do not apply it; record it under “Needs human decision”.

### What to check
1) Names
   - Folder names and filenames are in English.
   - Names are clear, professional, and consistent (avoid ambiguous abbreviations unless canonical).
2) Content (human-facing text)
   - Plain English by default; professional and academic tone.
   - Consistent terminology; define acronyms on first use and use them consistently.
   - Avoid idioms, slang, humor, or culturally-specific references.
3) Translation compliance (when applicable)
   - Canonical acronyms and technical names remain in English (e.g., ADR, RFC, API, CLI).
   - Code-adjacent text is not translated (code blocks, identifiers, flags, config keys, paths, errors).
4) Source code comments (when applicable)
   - Ensure comments and docstrings follow the language guidelines and the source code guidelines.
   - Remove or shorten verbose comments that do not add value.
   - Do not add comments for standard framework conventions.

### Working rules
- Audit and fix the entire repository (all folders and files). If there are binary or non-text files, fix naming only and record content as “not applicable”.
- Be precise and evidence-based. Do not guess.
- If you cannot access a file’s contents, stop and ask for what you need.
- Separate confirmed issues from suspected issues and open questions.
- Prefer minimal edits and renames. If a rename is risky (for example, a public API path), propose it under “Needs human decision” instead of applying it.

### Severity scale
- Blocker: violates a MUST requirement in the guidelines (for example, non-English paths, translated canonical acronyms, or translated code-adjacent text).
- High: likely to confuse readers or reduce professionalism in important documents.
- Medium: quality issues that should be fixed but are not critical.
- Low: minor typos or style inconsistencies.

### Output format
1) Plan (3–7 bullets)
2) Summary (2–6 sentences)
3) Changes applied
   - Renames (table: From | To | Rationale)
   - Content edits (table: Path | Section/excerpt | Change type | Rationale)
4) Remaining issues
   - Needs human decision (table: Path | Issue | Risk | Suggested next step)
5) Verification notes (what was checked; what could not be checked)
```
