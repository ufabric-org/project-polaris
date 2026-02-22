# Task Prompts

Task prompts are direct-use prompts intended to perform a specific task inside a repository (coding, review, documentation, or research). They should require minimal edits beyond providing the required inputs.

Task prompts are tailored for uFabric projects and SHOULD reference uFabric guidelines from the `ufabric-org/project-polaris` repository when defining rules or constraints.

## How to use a task prompt

1. Pick a `task-*.md` file from the list below.
2. Copy the **Prompt (copy/paste)** block into your LLM tool.
3. Provide the required inputs (if any) and the repository context.
4. These prompts assume that the project follows the [folder structure and files guidelines](https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/docs/project/folder-structure-and-files-guidelines.md).
5. Validate the output before merging changes (tests, checks, or manual verification).

## How to create a task prompt

Task prompts are shared assets across projects. Create them collaboratively:

1. Ask the maintainer what the prompt should do:
   - goal and scope
   - required inputs (files, links, context)
   - expected output format (and where it will be saved)
   - constraints (language, compatibility, security, performance)
   - validation requirements (tests, commands, acceptance criteria)
2. Write a prompt that is explicit, traceable, and safe:
   - require references to human source-of-truth documents
   - separate facts from assumptions
   - require clarifying questions when blocked
   - prefer minimal, reversible changes and explicit validation
3. Save it as `task-<name>.md` in this directory.

## Required sections (task prompts)

Each task prompt file MUST include:

- **Intent**
- **When to use**
- **Required inputs**
- **Output requirements**
- **Prompt (copy/paste)**

## Available task prompts

| Prompt                    | Primary use                                       | File                                |
| ------------------------- | ------------------------------------------------- | ----------------------------------- |
| Language guidelines enforcement | Enforce names and content language compliance | `task-language-guidelines-enforce.md` |
| Agentic folder bootstrap | Create or refresh `agentic/` runbooks and rule indexes | `task-agentic-folder-bootstrap.md` |
| Documentation coherence review | Review Markdown docs for coherence and ambiguity | `task-documentation-coherence-review.md` |
