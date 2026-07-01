# Thrive OS

Thrive OS is a personal and business operating system built on structured knowledge, disciplined execution, and AI collaboration.

## Governance

This repository is governed by [`CLAUDE.md`](CLAUDE.md). All contributors (human and AI) must follow it. The **Thrive Vault** (`vault/`) is the source of truth for architecture, decisions, and specifications — not chat history.

## Repository Structure

- `vault/` — The Thrive Vault (Obsidian). Constitution, vision, architecture, ADRs, specifications, projects, SOPs, AI notes, templates, and archive.
- `docs/` — Supporting documentation not held in the Vault.
- `apps/` — Application code.
- `automation/` — Automation scripts and workflows.
- `scripts/` — Standalone utility scripts.
- `database/` — Database schemas, migrations, and related assets.
- `docker/` — Containerization and deployment configuration.
- `tools/` — Internal tooling.

## Working Process

1. Read the Vault before implementing anything.
2. Follow approved specifications and ADRs.
3. Ask before making architectural changes.
4. Keep documentation in sync with implementation.

See `CLAUDE.md` for the full governing instructions.
