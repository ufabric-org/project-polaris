# Template Prompts

Template prompts are reusable scaffolds intended to be adapted into a task-specific prompt. They are most useful when you want consistent structure, constraints, and output formatting across repositories.

Template prompts are tailored for uFabric projects and SHOULD reference uFabric guidelines from the `ufabric-org/project-polaris` repository when defining reusable structure and constraints.

## How to use a template prompt

1. Pick a `template-*.md` file from the list below.
2. Copy the **Prompt (copy/paste)** block into your LLM tool.
3. Replace placeholders (e.g., `<TASK>`, `<REPO_CONTEXT>`, `<DEFINITION_OF_DONE>`).
4. Add links or excerpts from the relevant human source-of-truth documents.
5. Run the prompt and review the result critically.

## How to create a template prompt

Create templates collaboratively and keep them broadly applicable:

1. Ask the maintainer what the template should enable (and which tasks it should not cover).
2. Prefer stable placeholders and explicit output formats.
3. Require traceability to human source-of-truth documents.
4. Ensure the template is readable by humans and safe to apply.
5. Save it as `template-<name>.md` in this directory.

## Required sections (template prompts)

Each template prompt file MUST include:

- **Intent**
- **When to use**
- **Required inputs**
- **Output requirements**
- **Prompt (copy/paste)**

## Available template prompts

| Prompt | Primary use | File |
| --- | --- | --- |
| Coding task template | Scaffolding for coding tasks with tests/validation sections | `template-coding-task.md` |
| Research task template | Scaffolding for research tasks with traceability and evaluation sections | `template-research-task.md` |
| Review task template | Scaffolding for structured reviews with prioritized findings | `template-review-task.md` |
