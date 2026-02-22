# Security Policy

This document explains how to report security vulnerabilities for this repository.

## Supported versions

This repository is primarily documentation/research and is maintained by volunteers. Security fixes are handled on a best-effort basis.

| Version | Supported |
| --- | --- |
| `main` | ✅ |
| `gh-pages` | ✅ (if the repository uses it) |

## Reporting a vulnerability

Please **do not** open a public GitHub Issue for security vulnerabilities.

Preferred channels (in order):

- Use GitHub’s private vulnerability reporting: **“Report a vulnerability”** (Security tab).
- Email: `security@ufabric.org`

When reporting, include:

- a clear description of the impact
- affected files/paths and commit SHA (if known)
- reproduction steps or a proof-of-concept (redact secrets)
- suggested fix or mitigation (if you have one)

## Scope

We consider security issues to include (non-exhaustive):

- vulnerable dependencies and libraries
- exploitable code paths, build scripts, or automation (CI/CD)
- GitHub Actions or workflow misconfigurations that could lead to compromise
- incorrect documentation that could cause insecure deployments or unsafe operational practices
- prompt/agent instructions that could cause unsafe behavior (e.g., secret leakage, supply-chain risks)

## Disclosure and response

- We will acknowledge receipt within **1 week** (7 days).
- We will triage within **2 weeks** (14 days) from acknowledgement.
- We aim to ship a fix or mitigation within **2 additional weeks** (14 days) from triage.
- Maximum target end-to-end time: **5 weeks**.
- Please keep details private until a fix or mitigation is available.
