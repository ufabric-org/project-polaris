# Folder Structure and Files Guidelines

## Common

All projects MUST follow this folder and file structure guidance.
The table indicates which items are required, optional, or suggested; include only what is needed for the specific project.
Consider providing feedback on additional folders and files that may be needed, and the rationale for them.

> **Inclusion:** ✔️ required ➖ optional ➕ suggested
> **Scope:** 📦 common 🧪 research 🧱 code

## Cross-repository reuse (Polaris as upstream)

This repository (`ufabric-org/project-polaris`) is intended to be used as a starting point for other uFabric repositories.
Projects SHOULD share a consistent folder and file structure to make navigation easier for both humans and AI agents.

### Upstream-managed files (exact copies)

The table below includes an **Exact copy of** column.

If a file is copied from Polaris as an “exact copy”, downstream repositories MUST treat it as **upstream-managed**:

- **Do not modify it in the downstream repository.**
- If a change is required, make the change in Polaris first, then sync/update downstream copies.
- After updating shared human documentation in Polaris, refresh any agent-facing derived artifacts (for example, `agentic/`) so agents do not operate on stale rules.

### Project-specific files (local ownership)

Downstream repositories MAY add project-specific documentation, prompts, and templates when they are genuinely specific to that project.
If an artifact (prompt/template/guideline) is likely to be useful across multiple uFabric repositories, the preferred workflow is:

1) Add or update the shared artifact in Polaris.
2) Update Polaris agent-facing documentation (for example, `agentic/`).
3) Then continue implementation in the downstream repository using the updated shared reference.

<!-- #️⃣
Review the table below and ensure the descriptions are coherent and complete.
If a folder/file does not make sense, remove it.
#️⃣ -->

| Path                           | Filename                  | Inclusion | Scope | Description                                            | Exact copy of                                    | Based on                                               |
| :----------------------------- | :------------------------ | :-------: | :---: | :----------------------------------------------------- | :----------------------------------------------- | :----------------------------------------------------- |
| /                              | README.md                 |    ✔️     |  📦   | Contains a brief summary of the project.               |                                                  | templates/tpl-readme.md                                |
| /                              | AGENTS.md                 |     ➕     |  📦   | Agent instructions entry point for AI tools (see https://agents.md/). |                                                  | templates/tpl-agents.md                                |
| /                              | AGENT.md                  |     ➖     |  📦   | Optional alias for `AGENTS.md` for tools that only look for the singular form (symlink or copy), only if needed. |                                                  |                                                        |
| /                              | LICENSE                   |    ✔️     |  📦   | Project license file.                                  | ../../LICENSE                                    |                                                        |
| /                              | CHANGELOG.md              |     ➕     |  📦   | Overview of changes to the project's source files.     |                                                  | templates/changelog.md                                 |
| /                              | CONTRIBUTING.md           |     ➕     |  📦   | How to contribute to the project.                      | ../../CONTRIBUTING.md                            |                                                        |
| /                              | CODE_OF_CONDUCT.md        |     ➕     |  📦   | Code of conduct (expected community standards).        | ../../CODE_OF_CONDUCT.md                         |                                                        |
| /                              | SECURITY.md               |     ➕     |  📦   | Security policy and vulnerability reporting process.   | ../../SECURITY.md                                |                                                        |
| /                              | SUPPORT.md                |     ➕     |  📦   | How to support the project.                            | ../../SUPPORT.md                                 |                                                        |
| /                              | GOVERNANCE.md             |     ➕     |  📦   | Governance model and decision-making process.          | ../../GOVERNANCE.md                              |                                                        |
| /                              | ROADMAP.md                |     ➕     |  📦   | Roadmap for the project.                               |                                                  | templates/roadmap.md                                   |
| /                              | NOTICE                    |     ➕     |  📦   | Optional notices (attribution, legal, or third-party). |                                                  |                                                        |
| /                              | .gitignore                |     ➕     |  📦   | Ignore patterns for build artifacts and local files.   |                                                  |                                                        |
| /.github/ISSUE_TEMPLATE/       | bug_report.yml            |     ➖     |  📦   | Issue form for reporting docs/research/code problems.  | ../../.github/ISSUE_TEMPLATE/bug_report.yml      |                                                        |
| /.github/ISSUE_TEMPLATE/       | feature_request.yml       |     ➖     |  📦   | Issue form for proposing improvements (with criteria). | ../../.github/ISSUE_TEMPLATE/feature_request.yml |                                                        |
| /.github/ISSUE_TEMPLATE/       | question.yml              |     ➖     |  📦   | Issue form for questions (with context/outcome).       | ../../.github/ISSUE_TEMPLATE/question.yml        |                                                        |
| /.github/ISSUE_TEMPLATE/       | config.yml                |     ➖     |  📦   | Issue template settings + security contact links.      | ../../.github/ISSUE_TEMPLATE/config.yml          |                                                        |
| /.github/                      | PULL_REQUEST_TEMPLATE.md  |     ➖     |  📦   | PR template for consistent reviews and traceability.   | ../../.github/PULL_REQUEST_TEMPLATE.md           |                                                        |
| /.github/                      | CODEOWNERS                |     ➖     |  📦   | Default reviewers for paths (use as-is; update owners if needed). | ../../.github/CODEOWNERS                         |                                                        |
| /.github/workflows/            | security.yml              |     ➖     |  🧱   | Manual security scan workflow (CodeQL).                | ../../.github/workflows/security.yml             |                                                        |
| /docs/overview/                | mission-scope.md          |    ✔️     |  📦   | Project-specific mission scope.                        |                                                  | templates/overview-mission-scope.md                    |
| /docs/overview/                | principles.md             |    ✔️     |  📦   | Project-specific principles.                           |                                                  | templates/overview-principles.md                       |
| /docs/overview/                | glossary.md               |    ✔️     |  📦   | Project-specific glossary.                             |                                                  | templates/overview-glossary.md                         |
| /docs/overview/                | assumptions.md            |    ✔️     |  📦   | Project-specific assumptions.                          |                                                  | templates/overview-assumptions.md                      |
| /docs/guides/                  | getting-started.md        |     ➖     |  📦   | Project-specific getting started guide.                |                                                  | templates/guides-getting-started.md                    |
| /docs/guides/                  | troubleshooting.md        |     ➖     |  📦   | Project-specific troubleshooting guide.                |                                                  | templates/guides-troubleshooting.md                    |
| /docs/reference/               | configuration.md          |     ➖     |  📦   | Configuration reference (keys, defaults, examples).    |                                                  | templates/reference-configuration.md                   |
| /docs/reference/               | api.md                    |     ➖     |  🧱   | API reference (endpoints, schemas, error codes).       |                                                  | templates/reference-api.md                             |
| /docs/reference/official/      | README.md                 |     ➕     |  📦   | Index of included official documentation PDFs.         |                                                  |                                                        |
| /docs/reference/official/      | {tool}-{version}.pdf      |     ➕     |  📦   | Offline snapshot of official docs (if license allows). |                                                  |                                                        |
| /docs/architecture/            | README.md                 |    ✔️     |  📦   | Describes the project's high-level architecture.       |                                                  | templates/architecture-readme.md                       |
| /docs/architecture/c4model/    | context.md                |    ✔️     |  🧱   | C4 model: system context (actors, external systems).   |                                                  | templates/architecture-c4model-context.md              |
| /docs/architecture/c4model/    | container.md              |    ✔️     |  🧱   | C4 model: container view (services, stores, protocols). |                                                  | templates/architecture-c4model-container.md            |
| /docs/architecture/system/     | boundaries.md             |     ➖     |  🧱   | System boundaries and constraints.                     |                                                  | templates/architecture-system-boundaries.md            |
| /docs/architecture/system/     | quality-attributes.md     |     ➖     |  🧱   | Target quality attributes and trade-offs.              |                                                  | templates/architecture-system-quality-attributes.md    |
| /docs/architecture/runtime/    | environments.md           |     ➖     |  🧱   | Runtime environments (dev/stage/prod) and assumptions. |                                                  | templates/architecture-runtime-environments.md         |
| /docs/architecture/runtime/    | observability.md          |     ➖     |  🧱   | Observability approach (logs, metrics, tracing).       |                                                  | templates/architecture-runtime-observability.md        |
| /docs/architecture/runtime/    | reliability.md            |     ➖     |  🧱   | Reliability approach (SLOs, failover, resilience).      |                                                  | templates/architecture-runtime-reliability.md          |
| /docs/architecture/interfaces/ | api-contracts.md          |     ➖     |  🧱   | API contracts (schemas, compatibility expectations).   |                                                  | templates/architecture-interfaces-api-contracts.md     |
| /docs/architecture/interfaces/ | versioning-policy.md      |     ➖     |  🧱   | Versioning and compatibility policy.                   |                                                  | templates/architecture-interfaces-versioning-policy.md |
| /web/                          | index.md                  |     ➖     |  📦   | Website index/landing page content (only if needed).   |                                                  | templates/web-index.md                                 |
| /web/pages/                    | {page}.md                 |     ➖     |  📦   | Website page content (only if needed).                 |                                                  | templates/web-pages-page.md                            |
| /web/posts/                    | {post}.md                 |     ➖     |  📦   | Website post/article content (only if needed).         |                                                  | templates/web-pages-post.md                            |
| /web/assets/                   |                           |     ➖     |  📦   | Public web page assets.                                |                                                  | templates/web-pages-page.md                            |
| /src/                          |                           |    ✔️     |  🧱   | Project source code if needed.                         |                                                  |                                                        |
| /server/scripts/               | {bash-script}.sh          |     ➖     |  🧱   | Server installation scripts.                           |                                                  | templates/server-bash-script.md                        |
| /server/conf/                  | {file}.conf               |     ➖     |  🧱   | Server services configuration files.                   |                                                  |                                                        |
| /research/                     | README.md                 |    ✔️     |  🧪   | High-level rules for traceability and reproducibility. |                                                  |                                                        |
| /research/notes/               | {YYYYMMDD-note}.md        |     ➖     |  🧪   | Logs, lectures, ideas.                                 |                                                  |                                                        |
| /research/experiments/         | protocol.md               |     ➖     |  🧪   | Explains the protocol for the specific experiment.     |                                                  |                                                        |
| /research/experiments/runs/    | {YYYYMMDD-run-001}.md     |     ➖     |  🧪   | Experiment run results.                                |                                                  |                                                        |
| /research/datasets/            | README.md                 |     ➖     |  🧪   | Dataset origins, licenses, and checksums.              |                                                  | templates/dataset-readme.md                            |
| /research/datasets/raw/        |                           |     ➖     |  🧪   | Raw dataset files.                                     |                                                  |                                                        |
| /research/datasets/derived/    |                           |     ➖     |  🧪   | Derived dataset files.                                 |                                                  |                                                        |
| /research/bibliography/        | references.md             |     ➖     |  🧪   | Bibliography references (citations and sources).       |                                                  | templates/research-bibliography-references.md          |
| /research/bibliography/        | reading-list.md           |     ➖     |  🧪   | Reading list (papers, articles, and notes).            |                                                  | templates/research-bibliography-reading-list.md        |
| /research/papers/drafts/       | {draft}.md                |     ➖     |  🧪   | Paper drafts.                                          |                                                  | templates/research-papers-paper.md                     |
| /research/papers/submissions/  | {submitted}.md            |     ➖     |  🧪   | Paper submissions.                                     |                                                  |                                                        |
| /adr/                          | {adr-0001-description}.md |     ➖     |  📦   | Document project-wide architectural decision records.  |                                                  | templates/adr.md                                       |
