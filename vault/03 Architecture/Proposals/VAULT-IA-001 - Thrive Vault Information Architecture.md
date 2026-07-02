# Proposal: Thrive Vault Information Architecture

> This is an architecture proposal, not an implementation. It defines a candidate knowledge-organization structure for the Thrive Vault. Nothing described here has been created, renamed, or moved.

## ID
VAULT-IA-001

## Status
Draft

## Date
2026-07-02

## Owner
Founder

## Approver
Founder (Pending)

## Type
Architecture Proposal (knowledge architecture, not software architecture)

## Executive Summary
Introducing the System Definition as a new foundational document exposed a structural gap: the Vault's top-level folders are numbered contiguously (`01`, `02`, `03`, …), so a new foundational domain requires renumbering everything after it. This proposal designs the Vault's long-term top-level taxonomy once, deliberately, rather than renumbering incrementally each time a new domain is discovered. The recommendation keeps the existing domain set and their conceptual boundaries, adds two new foundational domains the ratified Constitution already anticipates (System Definition, Guiding Principles) plus Governance (also anticipated, kept distinct from Guiding Principles), and retains **contiguous numbering**: folder numbers represent conceptual order, not reserved insertion space, so introducing a new domain remains a deliberate architectural event handled by a proposal like this one. "Business" is not part of this taxonomy — the Vault governs Thrive OS itself, and business systems are applications of Thrive OS rather than part of its foundational knowledge architecture.

## Purpose
This document defines the long-term organization of the Thrive Vault as the permanent knowledge system for Thrive OS. It answers: what are the top-level knowledge domains, how should they be organized, which deserve their own numbered folder, which documents belong inside each, and how should future growth be accommodated — without prescribing software architecture, and without performing any restructuring itself.

## 1. Design Goals
- **Scalability** — new knowledge domains can be added over the system's life through a deliberate, well-defined process, even when doing so requires renumbering.
- **Discoverability** — a person unfamiliar with the Vault can find where a given piece of knowledge lives from the folder name and purpose alone.
- **Consistency** — every folder follows the same naming, numbering, and purpose-statement conventions.
- **AI retrieval** — folder purposes are distinct and testable enough that an AI system filing or retrieving a document can do so unambiguously from the folder's stated purpose.
- **Long-term maintainability** — the structure is expected to still make sense after years of accumulated documents, not just at its founding size.
- **Separation of concerns** — each folder owns exactly one kind of knowledge; relationships between domains are expressed as cross-references, not by blending content into a shared folder.

## 2. Design Principles
1. **One knowledge domain per top-level folder.** No folder serves two conceptually distinct purposes; if a folder's README needs "and" to describe its purpose, it is probably two domains.
2. **Contiguous, ordered numbering.** Top-level folder numbers represent the conceptual order of domains, from most foundational to most operational — not reserved insertion space. Introducing a new domain is a deliberate architectural event, addressed by a proposal like this one, not something the numbering scheme pre-allocates room for.
3. **Minimal cross-domain overlap.** Where two domains are conceptually adjacent (e.g. Constitution and Guiding Principles), their purpose statements must be written so that a document has exactly one correct home, testable by asking "would this also fit domain X's stated purpose?"
4. **Conceptual organization before implementation.** The taxonomy reflects knowledge domains — what kind of thing a document *is* — not software modules, org-chart structure, or tooling.
5. **Documentation-first organization.** A folder's purpose must be documented (its own README) before documents are placed inside it, mirroring the Constitution's Article V applied to the Vault's own structure.
6. **Archive is a one-way door.** Retired content moves to Archive and its folder number is permanently reserved; Archive itself is never renumbered, so nothing that has already been archived ever needs to move again.

## 3. Proposed Top-Level Taxonomy

| # | Folder | Purpose | Typical Contents |
|---|--------|---------|-------------------|
| 01 | Constitution | Supreme, rarely-amended governing document: purpose, principles, authority, source of truth. | `Constitution.md` |
| 02 | Vision | Long-term aspirational direction: what future Thrive OS is intended to create. | `Vision.md` |
| 03 | System Definition | Canonical conceptual answer to "what is Thrive OS": identity, boundaries, components, terminology. | `System Definition.md` |
| 04 | Guiding Principles | Enduring principles that inform judgment on matters the Constitution does not explicitly settle. *(New — not yet created.)* | `Guiding Principles.md` |
| 05 | Governance | The concrete decision-making, review, and amendment processes referenced as placeholders by Constitution Articles VI and VII. *(New — not yet created.)* | Governance process document(s) |
| 06 | Architecture | Current, as-built system architecture: components, data flow, technology stack. Includes `Proposals/` for architecture proposals not yet ratified (this document's own location). | `README.md`, `Proposals/*.md` |
| 07 | ADR | Architecture Decision Records: one file per ratified decision, numbered sequentially. | `ADR-NNNN - Title.md` |
| 08 | Specifications | Approved specifications implementation must follow. | `SPEC-XXXX-NNN - Title.md` |
| 09 | Projects | Active/planned projects: scope, status, owners, links to Specs/ADRs/commits. | `PRJ-NNNN - Title.md` |
| 10 | SOP | Repeatable procedures for recurring operational work. | `SOP - Title.md` |
| 11 | AI Collaboration | AI collaboration conventions, agent roles, prompting conventions, lessons learned. | Notes, conventions |
| 12 | Templates | Reusable note templates, one per document type used above. | `* Template.md` |
| 99 | Archive | Retired or superseded content from any domain. Position permanently reserved; never renumbered. | Retired documents |

Numbers are contiguous and represent conceptual order — most foundational (governing what Thrive OS is and why) first, most operational (day-to-day scaffolding) last, with Archive permanently fixed at `99` regardless of how many active domains exist.

## 4. Architectural Layers
This is a conceptual model only — it does not change folder numbering. It groups the taxonomy into two layers, describing *why* the domains fall in the order they do:

**Foundation** — Constitution, Vision, System Definition, Guiding Principles, Governance. These define the enduring identity and governance of Thrive OS: what it is, what future it is building toward, and how it is allowed to be governed and decided upon.

**Engineering** — Architecture, ADR, Specifications, Projects, SOP, AI Collaboration, Templates. These define how Thrive OS is designed, implemented, operated, and evolved, always within the boundaries the Foundation layer sets.

The Foundation layer changes rarely and deliberately; the Engineering layer changes continuously as work is done. No document in the Engineering layer may contradict a document in the Foundation layer, consistent with the Constitution's Article IV authority hierarchy.

## 5. Folder Responsibilities

- **Constitution** — non-negotiable, rarely-amended rules. Changes require the deliberate amendment process in Article VIII. The smallest, most stable domain by design.
- **Vision** — aspiration and direction. Expected to change more often than the Constitution but still infrequently; never contains process or implementation detail.
- **System Definition** — the conceptual "what," per `SPEC-SYSDEF-001`: identity, boundaries, components, terminology. Distinct from Vision (aspiration) and from Architecture (concrete, as-built design).
- **Guiding Principles** — defines enduring judgment: the principles that inform decisions on matters the Constitution does not explicitly settle, without themselves carrying constitutional weight or amendment procedure.
- **Governance** — defines formal decision processes: the concrete mechanics for how decisions, approvals, and amendments happen — the content the ratified Constitution's Article VI and Article VII already point to as "a dedicated governance document" and "a dedicated document" (AI Collaboration Conventions), respectively. Distinct from SOP: Governance covers how *architectural and directional* decisions are made; SOP covers how *recurring operational* work is done.
- **Architecture** — the current, approved, as-built design. Changes flow through ADRs. Its `Proposals/` subfolder holds architecture proposals (like this one) that have not yet been ratified.
- **ADR** — the historical record of each ratified architectural decision, including decisions that change Architecture or the Vault's own taxonomy.
- **Specifications** — implementation contracts: what must be built, not how.
- **Projects** — the work container: links every ADR, Specification, meeting, and commit belonging to one initiative.
- **SOP** — repeatable operational procedures, distinct from Governance's decision-making processes.
- **AI Collaboration** — collaboration conventions and lessons specific to working with AI systems, referenced by the Constitution's Article VII.
- **Templates** — scaffolding only; never contains live project or governance content.
- **Archive** — retired content from any domain; nothing here is current.

Business systems are not a Vault domain. The Vault governs Thrive OS itself; business systems are applications built and run using Thrive OS, not part of its foundational knowledge architecture. Business-related work is tracked like any other application of the system — through `Projects` — not through a dedicated top-level folder.

## 6. Naming Conventions
- **Folders:** `NN Name/` — a zero-padded number followed by a space and a Title Case name, matching the existing convention (`01 Constitution`, `05 Vision`, …).
- **Singular foundational documents:** Title Case with spaces, no ID prefix, one per folder (e.g. `Constitution.md`, `Vision.md`, `System Definition.md`).
- **Identifier-bearing documents:** `PREFIX-DOMAIN-NNN - Title.md` for Specifications and cross-cutting proposals (e.g. `SPEC-CONST-001 - Constitution.md`, `VAULT-IA-001 - Thrive Vault Information Architecture.md`), and `ADR-NNNN - Title.md` for ADRs, consistent with the existing ADR Template's `ADR NNNN: Title` heading.
- **Identifier registry:** a single canonical list of active ID prefixes (`SPEC-`, `ADR-`, `PRJ-`, `VAULT-`, and any future prefix) should be maintained so new domains cannot silently collide with an existing prefix.
- **Numbering:** top-level folders use contiguous two-digit numbers reflecting conceptual order (Design Principle 2); document IDs within a domain are sequential, zero-padded, and never reused, even if the document is later moved to Archive.

## 7. Migration Strategy
Described for future reference only — not performed as part of this proposal:
1. Approve this proposal (Founder ratification).
2. Create the new folders at their proposed numbers, each with its own README stating its purpose.
3. Move existing documents into their new folder locations using version-control-preserving moves, not copy-and-delete.
4. Audit and update every internal cross-reference (relative Markdown links) across all moved documents in the same change.
5. Update the folder-structure listings in the Vault's own `README.md`, `CONTRIBUTING.md`, and `CLAUDE.md` to match.
6. Confirm no dangling references remain before considering the migration complete.

## 8. Risks
- **Future renumbering** — contiguous numbering means introducing a new foundational domain will require renumbering subsequent folders again, as it did in this milestone. This is accepted as the deliberate cost of numbers that mean something (conceptual order), rather than engineered away with reserved gaps.
- **Domain overlap** — Constitution / Guiding Principles / Governance is the most overlap-prone boundary in this taxonomy; the responsibility statements above are written to keep it testable, but should be re-checked once Guiding Principles and Governance are actually drafted.
- **Broken references** — any migration invalidates relative links between moved documents; mitigated by treating migration as a single atomic change with a full link audit (Migration Strategy, step 4), not an incremental drift.
- **AI retrieval ambiguity** — if two folders' purpose statements read similarly, automated filing or retrieval may misplace new content; mitigated by the testability requirement in Design Principle 3, but not yet verified against the Guiding Principles / Governance boundary specifically.
- **Scalability** — a finite, contiguous number space means the taxonomy will need deliberate renumbering again if enough new domains are added; accepted as inherent to this numbering choice.

## 9. Deferred Decisions
- Whether `Architecture/Proposals/` remains a subfolder of Architecture or becomes its own top-level domain is deferred until proposal volume justifies revisiting it.
- The exact form and location of the identifier-prefix registry document is deferred to implementation.

## 10. Open Questions
None remaining. The prior open items have been resolved by architectural decision: numbering remains contiguous; Business is excluded from the taxonomy; Guiding Principles and Governance remain separate domains.

## 11. Acceptance Criteria
- [ ] Every top-level folder maps to exactly one knowledge domain with a non-overlapping purpose statement.
- [ ] Every Vault document that exists as of this proposal has an unambiguous new home in the proposed structure.
- [ ] The taxonomy's treatment of Constitution, Guiding Principles, and Governance is resolved with testable, non-overlapping purpose statements.
- [ ] The taxonomy defines a naming convention applicable to all current and reasonably foreseeable future document types.
- [ ] The proposal identifies a migration path that risks no data loss and accounts for link integrity.
- [ ] The structure remains legible to a human skimming folder names and to an AI system retrieving by folder purpose alone.

## References
- [`vault/01 Constitution/Constitution.md`](../../01%20Constitution/Constitution.md)
- [`vault/02 Vision/Vision.md`](../../02%20Vision/Vision.md)
- [`vault/05 Specifications/SPEC-SYSDEF-001 - System Definition.md`](../../05%20Specifications/SPEC-SYSDEF-001%20-%20System%20Definition.md) — the specification whose Vault-placement dependency triggered this proposal.
- [`vault/README.md`](../../README.md) — current Vault structure this proposal reconsiders.
- [`CONTRIBUTING.md`](../../../CONTRIBUTING.md)
- [`CLAUDE.md`](../../../CLAUDE.md)
