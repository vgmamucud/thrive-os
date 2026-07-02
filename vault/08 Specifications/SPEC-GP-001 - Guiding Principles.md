# Specification: Thrive OS Guiding Principles

> A Specification defines **what must be implemented**, not **how it is implemented**. Architectural rationale belongs in an ADR (`07 ADR/`), operational procedures belong in governance documents, and implementation details belong in technical design or code.

## ID
SPEC-GP-001

## Version
1.0.0

## Status
Approved

## Date
2026-07-02

## Owner
Founder

## Approver
Founder

## Priority
Critical

## Summary
This specification defines the required structure and content constraints for the Thrive OS Guiding Principles — the foundational document that provides decision heuristics for matters the Constitution intentionally leaves unsettled. It does not contain the Guiding Principles' actual prose; it defines what that document must contain so it can be drafted, reviewed, and approved before implementation, consistent with the Constitution's Article V (Documentation-First Development). Guiding Principles occupies the Foundation layer alongside the Constitution, Vision, System Definition, and Governance, per `VAULT-IA-001`, and must remain sharply distinguished from all four.

## Goals
- Specify every section the Guiding Principles document must include, in order.
- Establish, unambiguously, that Guiding Principles exists to provide **decision heuristics** — guidance for reasoning — precisely where the Constitution is silent, not to create new rules, procedures, identity claims, or implementation guidance.
- Require the future document to explicitly disambiguate itself from the Constitution's Article II ("Core Principles"), given the name-adjacency risk identified during architectural review of Milestone 3D.
- Require the future document to explicitly state its boundary against Governance, System Definition, and Architecture, so a reader can place any given piece of guidance in exactly one document.
- Provide enough precision that Guiding Principles can be implemented without further clarification once this spec is approved.

## Non-Goals
- Writing the Guiding Principles' actual prose (that is the implementation step, gated on approval of this spec).
- Defining or amending any Constitutional rule, principle, or authority structure — those remain owned by `01 Constitution/Constitution.md` and can only change through Article VIII's amendment procedure.
- Defining decision-making process, review steps, or amendment mechanics — those belong to `05 Governance/`.
- Defining Thrive OS's conceptual identity, boundaries, or components — those belong to `03 System Definition/`.
- Defining technical architecture, technology choices, or implementation detail — those belong to `06 Architecture/` and ADRs.
- Resolving the relationship between this Vault domain and the principle-like content already present in the repository root's `CLAUDE.md` (its "Engineering Principles" and "Decision Boundaries" sections) — deferred (see Deferred Decisions).

## Functional Requirements
The Guiding Principles document must contain the following sections, in this order:

1. **Title** — identifies the document as the Thrive OS Guiding Principles.
2. **Metadata** — document identity fields (status, version, ratification date, owner, implements) consistent with other ratified Vault documents.
3. **Purpose of Guiding Principles** — states why this document exists: to provide decision heuristics for matters the Constitution does not explicitly settle, and how it relates to the Constitution, Vision, System Definition, Governance, and Architecture.
4. **Scope of Guiding Principles** — states what kinds of judgment calls this document covers (recurring, non-constitutional decisions requiring consistent reasoning) and what kinds it does not.
5. **Relationship to the Constitution** — defines the relationship between the Constitution's Core Principles and Guiding Principles in terms of authority, not hierarchy: Core Principles are authoritative constitutional commitments. Guiding Principles are decision heuristics that operate only where constitutional commitments do not prescribe a single course of action. Guiding Principles may never contradict, weaken, or reinterpret the Constitution.
6. **Guiding Principles** — the enumerated heuristics themselves. Each principle must be stated as reasoning guidance (what to weigh, prefer, or consider) rather than as a rule ("must never X") or a procedure ("when X, do Y, then Z"), and should include a brief rationale.
7. **Relationship to the Vision** — states that Guiding Principles must remain consistent with the Vision without restating its aspirational content; principles describe how to reason in the present, not the future Thrive OS is building toward.
8. **Relationship to the System Definition** — states that Guiding Principles must not restate or extend the System Definition's Identity, Core Components, or System Boundaries sections; it may reference them but must not redefine them.
9. **Relationship to Governance** — states that Guiding Principles may inform how a Governance process is exercised (e.g. what a reviewer should weigh) but must never itself specify who decides, in what sequence, or under what procedure — that content belongs exclusively to Governance.
10. **Relationship to Architecture** — states that Guiding Principles must not reference specific technologies, implementation patterns, or architectural components; where a principle bears on engineering judgment (e.g. preferring simplicity), it must be stated abstractly enough to apply regardless of the technology in use.
11. **Non-Goals** — states what Guiding Principles explicitly does not cover, restating the boundary against Constitution, Governance, System Definition, and Architecture from the perspective of the document itself.
12. **Appendix — Definitions** — defines any terms introduced in Guiding Principles not already defined in the Constitution's, Vision's, or System Definition's Appendices.

## Non-Functional Requirements
- **Heuristic language:** each principle must be phrased as guidance for judgment ("should," "prefer," "weigh," "favor") rather than as obligation language ("must," "shall") reserved for constitutional rules, except where restating that the Constitution takes precedence.
- **No procedural content:** the document must not describe decision-making steps, approval sequences, review cadence, or amendment mechanics — any such content belongs to Governance and must be flagged as a defect if found here.
- **No immutable rules:** the document must not state a rule that Thrive OS may never violate — anything phrased that way belongs in the Constitution, subject to Article VIII amendment, not here.
- **No identity definitions:** the document must not define what Thrive OS is, its boundaries, or its components — those are owned by the System Definition.
- **No implementation guidance:** the document must not reference specific code, file paths, schemas, configuration, or technology/vendor choices.
- **Vendor independence:** the document must remain technology-agnostic throughout.
- **Lighter revisability than the Constitution:** the document should be revisable through the standard Documentation-First discipline (Article V) without invoking the Constitution's Article VIII amendment procedure, since it carries no constitutional weight — but any revision must still be a deliberate, recorded change, never inferred from silence.
- **Internal consistency:** no principle may contradict another principle in the same document.
- **Consistency with the Constitution, Vision, and System Definition:** no statement may contradict `01 Constitution/Constitution.md`, `02 Vision/Vision.md`, or `03 System Definition/System Definition.md`.
- **Standalone readability:** the document must be understandable without requiring the reader to first read Governance or Architecture documents.
- **Markdown standards:** the document must follow the Vault's existing Markdown conventions.

## Dependencies
- `01 Constitution/Constitution.md` (Ratified, v1.0.0) — satisfied.
- `02 Vision/Vision.md` (Ratified, v1.0.0) — satisfied.
- `03 System Definition/System Definition.md` (Ratified, v1.0.0) — satisfied.
- The top-level folder `vault/04 Guiding Principles/` already exists, per the Milestone 3B.5 Vault migration — satisfied.
- No Governance or Architecture document is required to exist before this specification can be approved; Guiding Principles is intended to precede and inform Governance's exercise of judgment, not depend on it.

## Risks
- **Name collision with Article II ("Core Principles"):** the most significant identified risk — mitigated by the mandatory disambiguation required in Functional Requirement 5.
- **Drift into procedural content:** a principle intended as judgment guidance ("prefer the simplest approach that satisfies the spec") can easily be drafted as an implicit procedure ("when a spec is ambiguous, do X then Y") — mitigated by the Non-Functional Requirement barring procedural content and the heuristic-language requirement.
- **Drift into constitutional rule-making:** a principle can be phrased strongly enough ("must never...") that it functions as an unamendable rule in practice even without Article VIII backing — mitigated by the heuristic-language requirement restricting "must/shall" to statements restating constitutional precedence.
- **Overlap with System Definition's Identity section:** a principle explaining *why* a System Definition identity property matters risks re-describing that property — mitigated by Functional Requirement 8's explicit boundary.
- **CLAUDE.md relationship left unresolved:** `CLAUDE.md`'s existing "Engineering Principles" and "Decision Boundaries" sections are not part of the Vault and are not addressed by this specification — accepted as a Deferred Decision, not a blocker, since `CLAUDE.md` governs repository-level AI collaboration conventions, not Vault content, and reconciling the two is a separate architectural question.

## Open Questions
None remaining. All items raised during the Milestone 3D architectural review have been resolved:
- **Article II disambiguation:** resolved by making it a mandatory Functional Requirement (Section 5) rather than leaving it as an open question.
- **CLAUDE.md relationship:** resolved as a Deferred Decision — it does not block this specification's approval or the future Guiding Principles document's implementation.

## Deferred Decisions
- Whether and how `CLAUDE.md`'s "Engineering Principles" and "Decision Boundaries" sections should be reconciled with, referenced by, or migrated into the Vault's Guiding Principles domain is deferred to future architectural work.
- The exact number and enumeration of principles in the future Guiding Principles document is left to implementation, provided each satisfies this specification's Functional and Non-Functional Requirements.
- The exact list of terms requiring definition in the Appendix is left to implementation, provided every term introduced and used normatively is defined either there or by reference to an existing Constitution, Vision, or System Definition Appendix entry.

## Acceptance Criteria
- [ ] All twelve required sections are present, in the specified order.
- [ ] The document explicitly states that Guiding Principles provides decision heuristics for matters the Constitution intentionally leaves unsettled.
- [ ] The document explicitly disambiguates itself from the Constitution's Article II ("Core Principles").
- [ ] No principle is phrased as a procedural step, approval sequence, or amendment mechanic (Governance content).
- [ ] No principle is phrased as an immutable, amendment-gated rule (Constitution content).
- [ ] No section defines Thrive OS's identity, boundaries, or components (System Definition content).
- [ ] No section references specific technology, implementation patterns, or vendor choices (Architecture content).
- [ ] Every principle is stated as heuristic guidance with a brief rationale, using "should/prefer/weigh/favor" language rather than "must/shall" (except where restating constitutional precedence).
- [ ] No section contradicts the Constitution, the Vision, or the System Definition.
- [ ] The document reads as a complete, self-contained set of decision heuristics without needing external context to understand its intent.
- [ ] The rendered file passes Markdown formatting review (heading levels, list syntax, no broken links).

## Traceability
- Origin: Founder architectural discussion — Milestone 3D, following Milestone 3A (Constitutional Foundation), Milestone 3B (Vision), Milestone 3B.5 (Information Architecture Ratification & Repository Migration), and Milestone 3C (System Definition).
- Governing document(s): `01 Constitution/Constitution.md` (v1.0.0, Ratified); `02 Vision/Vision.md` (v1.0.0, Ratified); `03 System Definition/System Definition.md` (v1.0.0, Ratified); `VAULT-IA-001` (Ratified); `CLAUDE.md`; `CONTRIBUTING.md`.
- Implementation target: `vault/04 Guiding Principles/Guiding Principles.md`.
- Future ADR references: TBD.

## References
- [`vault/01 Constitution/Constitution.md`](../01%20Constitution/Constitution.md) — supreme governing reference this specification and the future Guiding Principles must remain consistent with; source of the Article II name-adjacency this specification requires disambiguating.
- [`vault/02 Vision/Vision.md`](../02%20Vision/Vision.md) — aspirational reference this specification's future implementation must remain consistent with.
- [`vault/03 System Definition/System Definition.md`](../03%20System%20Definition/System%20Definition.md) — conceptual reference this specification's future implementation must not duplicate.
- [`vault/06 Architecture/Proposals/VAULT-IA-001 - Thrive Vault Information Architecture.md`](../06%20Architecture/Proposals/VAULT-IA-001%20-%20Thrive%20Vault%20Information%20Architecture.md) — ratified taxonomy establishing Guiding Principles as a distinct Foundation-layer domain.
- [`vault/04 Guiding Principles/README.md`](../04%20Guiding%20Principles/README.md) — current folder placeholder; implementation target's containing folder.
- [`vault/08 Specifications/SPEC-SYSDEF-001 - System Definition.md`](SPEC-SYSDEF-001%20-%20System%20Definition.md) — prior specification in this Documentation-First sequence, for structural precedent.
- [`CONTRIBUTING.md`](../../CONTRIBUTING.md) — repository workflow this specification follows.
- [`CLAUDE.md`](../../CLAUDE.md) — governing instructions for implementation work; contains pre-existing principle-like content whose relationship to this domain is a Deferred Decision.
