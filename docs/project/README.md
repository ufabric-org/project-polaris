# Project Guidelines

This directory contains the cross-project guidelines and references that uFabric repositories MUST follow.

## Entry points

- AI usage: [docs/project/ai-guidelines.md](ai-guidelines.md)
- Language and terminology: [docs/project/language-guidelines.md](language-guidelines.md)
- Source code conventions: [docs/project/source-code-guidelines.md](source-code-guidelines.md)
- Default technical choices: [docs/project/technical-guidelines.md](technical-guidelines.md)
- Cross-repo structure and upstream-managed copies: [docs/project/folder-structure-and-files-guidelines.md](folder-structure-and-files-guidelines.md)
- Prompt library rules: [docs/project/prompts/README.md](prompts/README.md)
- Agent instructions convention (`AGENTS.md`): [docs/project/folder-structure-and-files-guidelines.md](folder-structure-and-files-guidelines.md)

## General guidelines

0. All uFabric projects MUST follow the publicly available guidelines in [this repository](https://raw.githubusercontent.com/ufabric-org/project-polaris/refs/heads/main/README.md).
1. All projects MUST exist in the [ufabric-org organization](https://github.com/ufabric-org) currently hosted on GitHub.
2. All projects MAY use AI for content, code, and image generation according to the [AI - LLMs and other tools](ai-guidelines.md) guidelines.
3. All documents MUST be written in English according to the [language guidelines](language-guidelines.md).
4. All projects MUST follow the [technical guidelines](technical-guidelines.md).
5. All projects MUST have a CHANGELOG following the [keepachangelog.com/en/1.1.0](https://keepachangelog.com/en/1.1.0/) conventions.
6. Repositories bootstrapped from Polaris SHOULD keep shared structure for navigation. Files that are exact copies from Polaris MUST NOT be modified downstream; changes must be made in Polaris and then synced.
