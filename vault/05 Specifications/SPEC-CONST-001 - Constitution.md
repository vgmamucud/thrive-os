# Specification: Thrive OS Constitution

> A Specification defines **what must be implemented**, not **how it is implemented**. Architectural rationale belongs in an ADR (`04 ADR/`), operational procedures belong in governance documents, and implementation details belong in technical design or code.

## ID
SPEC-CONST-001

## Version
1.0.0

## Status
Approved

## Date
2026-07-01

## Owner
Founder

## Approver
Founder

## Priority
Critical

## Summary
This specification defines the required structure and content constraints for the Thrive OS Constitution — the foundational, rarely-changed governing document that establishes the system's purpose, principles, authority, source of truth, development approach, governance process, AI-collaboration expectations, and amendment procedure. It does not contain the Constitution's text; it defines what the Constitution must contain so it can be drafted, reviewed, and approved before implementation.

## Goals
- Specify every section the Constitution must include, in order.
- Specify the language, tone, and scope constraints the Constitution must satisfy.
- Provide enough precision that the Constitution can be implemented without further clarification once this spec is approved.

## Non-Goals
- Writing the Constitution's actual prose (that is the implementation step, gated on approval of this spec).
- Specifying implementation details, specific vendors, tools, or technology choices — the Constitution must remain vendor-independent; any such detail belongs in ADRs, Architecture docs, or SOPs.
- Defining the governance process mechanics in full (e.g. voting procedures, meeting cadence) — only that a governance process must exist and be referenced; mechanics belong in a future SOP or governance document.

## Functional Requirements
The Constitution must contain the following sections, in this order:

1. **Title** — identifies the document as the Thrive OS Constitution.
2. **Metadata** — document identity fields (e.g. status, version/date, ratification info) consistent with other Vault documents.
3. **Preamble** — a short statement of intent framing why the Constitution exists.
4. **Article I — Purpose** — states the reason Thrive OS exists.
5. **Article II — Core Principles** — the non-negotiable values and principles governing all work.
6. **Article III — Authority** — establishes what the Constitution governs and its precedence relative to other Vault documents.
7. **Article IV — Source of Truth** — establishes the Vault as the authoritative source of truth over chat history or memory.
8. **Article V — Documentation-First Development** — establishes that specifications and documentation precede implementation.
9. **Article VI — Governance** — establishes how decisions are made and by whom, at a principle level (not process mechanics).
10. **Article VII — AI Collaboration** — establishes the expectations and boundaries for AI-assisted work within the system.
11. **Article VIII — Constitutional Amendments** — establishes how the Constitution itself may be changed.
12. **Appendix — Definitions** — defines key terms used throughout the document.

## Non-Functional Requirements
- **Normative language:** the document must use "must," "shall," and "may" consistently and correctly to express obligation, requirement, and permission.
- **Concision:** the Constitution must stay short enough to be read in full in one sitting; it is a foundational reference, not a detailed procedural manual.
- **No implementation details:** the document must not reference specific code, file paths, schemas, or configuration.
- **Vendor independence:** technology references, where unavoidable, must be described generically (e.g. "a version-controlled repository," "a structured knowledge base") rather than naming specific products or vendors.
- **Cross-referencing:** the document must reference related future governance documents (e.g. governance process details, AI collaboration conventions) using placeholder links where those documents do not yet exist, rather than inlining their content.
- **Markdown standards:** the document must follow the Vault's existing Markdown conventions (heading hierarchy, no unsupported syntax).

## Dependencies
- None required to approve this specification. The following are needed before Article VI and Article VII cross-references can resolve to real documents, but their absence does not block drafting the Constitution with placeholder links:
  - A future Governance Process document (referenced by Article VI).
  - A future AI Collaboration Conventions document in `08 AI/` (referenced by Article VII).

## Risks
- A Constitution kept deliberately concise and vendor-independent may read as abstract or under-specified to implementers used to detailed specs — accepted as inherent to the Constitution's role as a foundational, rarely-changed document, not a procedural one.
- Placeholder cross-references to not-yet-written governance documents could be forgotten and never filled in — mitigated by tracking resolution of the placeholders as a Deferred Decision (see below).

## Open Questions
None remaining. All items raised during review have been resolved (see Deferred Decisions and Traceability):
- No ADR is required — this work implements an already-approved specification and does not introduce a new architectural decision.
- No separate Project entry is required — the Constitution is part of Milestone 3 and does not need its own project artifact.

## Deferred Decisions
- The exact wording and enumeration of terms in the Appendix — Definitions section is left to implementation, provided every term used normatively elsewhere in the document is defined.
- Governance process mechanics (e.g. how amendments are proposed, discussed, and ratified beyond the high-level rule in Article VIII) are deferred to a future governance document rather than specified here.
- Placeholder cross-references in Article VI and Article VII are not approval blockers; they will be resolved as the remaining foundational governance documents (a Governance Process document and an AI Collaboration Conventions document in `08 AI/`) are created.

## Acceptance Criteria
- [ ] All twelve required sections are present, in the specified order.
- [ ] Every obligation in the document is expressed with "must," "shall," or "may."
- [ ] No section references a specific tool, vendor, file path, or implementation mechanism.
- [ ] The document reads as a complete, self-contained constitution without needing external context to understand its intent.
- [ ] Placeholder cross-references exist for any future governance document mentioned but not yet written.
- [ ] The rendered file passes Markdown formatting review (heading levels, list syntax, no broken links).

## Traceability
- Origin: Founder architectural discussion.
- Governing document(s): Thrive OS Development Methodology; `CLAUDE.md`; `CONTRIBUTING.md`.
- Implementation target: `vault/01 Constitution/Constitution.md`.
- Future ADR references: TBD.

## References
- [`vault/01 Constitution/README.md`](../01%20Constitution/README.md) — current folder placeholder; implementation target for this specification.
- [`vault/README.md`](../README.md) — Vault structure overview.
- [`CONTRIBUTING.md`](../../CONTRIBUTING.md) — repository workflow this specification follows.
- [`CLAUDE.md`](../../CLAUDE.md) — governing instructions for implementation work.
