# Contributing to Thrive OS

Thrive OS is governed by [`CLAUDE.md`](CLAUDE.md). This document describes how work — human or AI — should flow through the repository day to day. If anything here conflicts with `CLAUDE.md`, `CLAUDE.md` wins.

## Roles

- **Architecture** (ChatGPT, or the human owner) — owns the Constitution, Vision, Architecture, and ADRs. Architectural changes originate here, not in implementation work.
- **Implementation** (Claude Code, or the human owner) — implements approved specifications, writes production code, keeps documentation in sync, and recommends improvements without unilaterally redesigning the system.

The Vault (`vault/`) is the source of truth for both roles. Do not rely on prior chat history — if the Vault and a conversation disagree, the Vault wins and the conflict should be resolved by updating the Vault, not by trusting memory.

## How Work Flows

A **Project** (`06 Projects/`) is the container for all work — ADRs, Specifications, Meetings, and Commits belong to a Project, rather than a Project being assembled after the fact from a Specification. The flow:

```
Idea
→ Constitution & Vision Check
→ Project Created
→ Architectural Impact?
    • Yes → Create/Approve ADR
    • No  → Continue
→ Specification
→ Implementation
→ Documentation Synchronization
→ Architecture Review
→ Approval
→ Git Commit
```

1. **Idea or problem surfaces.** Check it against `01 Constitution/` and `02 Vision/` — does it fit where Thrive OS is going?
2. **Create the Project.** Open a note in `06 Projects/` using `09 Templates/Project Template.md` before any ADR, spec, or code exists. It holds the project ID, sponsor, priority, target outcome, and will accumulate links to every ADR, Specification, Meeting, and commit that belongs to this work.
3. **Architectural impact?** If the change affects system structure, data flow, or technology choices, it needs an ADR in `04 ADR/` before implementation starts. Use `09 Templates/ADR Template.md` and link it from the Project. Small, non-architectural changes can skip straight to the next step.
4. **Write or update a specification.** Implementable work should be described in `05 Specifications/` precisely enough to build against without further clarification. Use `09 Templates/Specification Template.md` and link it from the Project.
5. **Implement.** Build against the approved specification. Prefer clarity over cleverness; keep changes modular, readable, and testable. Do not introduce new technologies or architectural changes outside of an approved ADR.
6. **Keep documentation synchronized.** If implementation reveals the spec or architecture was wrong or incomplete, update the Vault as part of the same change — don't let docs drift from reality.
7. **Architecture review.** Confirm the implementation still matches the approved ADR(s) and Specification before requesting approval.
8. **Approval.** Get sign-off (the human owner, per `CLAUDE.md`'s decision boundaries) before committing.
9. **Git commit.** Reference the Project (and its ADR/Specification, if applicable) in the commit message, then update `CHANGELOG.md` under `[Unreleased]`, following [Keep a Changelog](https://keepachangelog.com/).

Recurring procedures and meetings still hang off the Project as they come up: anything done more than once that shouldn't depend on memory belongs in `07 SOP/` (`09 Templates/SOP Template.md`); discussions worth preserving use `09 Templates/Meeting Notes Template.md`; AI-collaboration lessons go in `08 AI/`.

## Ground Rules

- Ask before making architectural changes; don't infer approval from silence.
- State assumptions explicitly when a specification is incomplete rather than guessing silently.
- Reference the relevant ADR or specification in commit messages and project notes when applicable.
- Recommendations for improvement belong in a "Recommendations" section of your output, or a new Vault note — not folded silently into an unrelated change.
- Build for the next ten years, not the next ten minutes.

## Commits

Keep commits scoped to a single logical change. Write commit messages that explain *why*, not just *what* — the diff already shows what changed.
