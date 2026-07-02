# Changelog

All notable changes to this repository are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), adapted for Thrive OS's current architectural phase: entries are grouped by **Milestone** rather than semantic version, since the project has no release/tagging process yet. That may change via ADR once one is defined.

## [Unreleased] — Milestone 3B.5 — Information Architecture Ratification & Repository Migration

### Changed
- Ratified `VAULT-IA-001 - Thrive Vault Information Architecture` (Status: Draft → Ratified) and approved `SPEC-SYSDEF-001 - System Definition` (Status: Draft → Approved, v1.0.0).
- Migrated the Vault's top-level taxonomy to match the ratified structure: added `03 System Definition/`, `04 Guiding Principles/`, `05 Governance/`; renumbered `03 Architecture/`→`06 Architecture/`, `04 ADR/`→`07 ADR/`, `05 Specifications/`→`08 Specifications/`, `06 Projects/`→`09 Projects/`, `07 SOP/`→`10 SOP/`, `08 AI/`→`11 AI Collaboration/`, `09 Templates/`→`12 Templates/` (all moves preserved via `git mv`).
- Updated every internal cross-reference to the renumbered folders across the Vault, `README.md`, and `CONTRIBUTING.md`.

## [Unreleased] — Milestone 2 — Repository Foundation

### Added
- `CONTRIBUTING.md` describing how work flows through Thrive OS (architecture → ADR → specification → project → implementation → docs sync).
- `CHANGELOG.md` (this file).
- `vault/README.md` indexing the Vault structure.
- Templates for Projects, SOPs, and Meeting Notes in `vault/09 Templates/`, alongside the existing ADR and Specification templates.

## Milestone 1 — Repository Initialization

### Added
- Initial repository scaffold: `vault/`, `docs/`, `apps/`, `automation/`, `scripts/`, `database/`, `docker/`, `tools/`, each with a README.
- Governing `CLAUDE.md`, root `README.md`, `LICENSE`, and `.gitignore`.
- ADR and Specification templates in `vault/09 Templates/`.
