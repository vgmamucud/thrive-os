# Specification: Thrive OS Governance

> A Specification defines **what must be implemented**, not **how it is implemented**. Architectural rationale belongs in an ADR (`07 ADR/`), operational procedures belong in governance documents, and implementation details belong in technical design or code.

## ID
SPEC-GOV-001

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
This specification defines the required structure and content constraints for the Thrive OS Governance document — the foundational document that operationalizes the decision-making, review, approval, and amendment processes the Constitution's Article VI and Article VIII require but do not themselves specify. It does not contain Governance's actual prose; it defines what that document must contain so it can be drafted, reviewed, and approved before implementation, consistent with the Constitution's Article V (Documentation-First Development). Governance occupies the Foundation layer alongside the Constitution, Vision, System Definition, and Guiding Principles, per `VAULT-IA-001`, and must remain sharply distinguished from all four, from Architecture, and from the repository's `CONTRIBUTING.md`.

## Goals
- Specify every section the Governance document must include, in order.
- Establish, unambiguously, that Governance defines *mechanics* — who decides, in what sequence, under what authority, with what artifact as the record — never substance already settled by the Constitution, aspiration already stated by the Vision, identity already defined by the System Definition, or judgment heuristics already provided by Guiding Principles.
- Require the future document to explicitly state its relationship to Article VIII, making clear that Governance operationalizes the constitutional amendment procedure but may never weaken or reinterpret constitutional requirements.
- Require the future document to explicitly distinguish itself from `CONTRIBUTING.md`, so repository contribution mechanics and Thrive OS governance are never conflated.
- Require the future document to define artifact-specific lifecycle models rather than a single unified status vocabulary, preserving the distinct conventions already established for Foundation documents, Specifications, ADRs, and Projects.
- Provide enough precision that Governance can be implemented without further clarification once this spec is approved.

## Non-Goals
- Writing Governance's actual prose (that is the implementation step, gated on approval of this spec).
- Defining or amending any Constitutional rule, principle, or authority structure — those remain owned by `01 Constitution/Constitution.md` and can only change through Article VIII's amendment procedure.
- Restating the Vision's aspiration, the System Definition's identity content, or Guiding Principles' decision heuristics.
- Defining technical architecture, technology choices, or implementation detail — those belong to `06 Architecture/` and ADRs.
- Unifying the Foundation, Specification, ADR, and Project status vocabularies into a single scheme — each artifact type keeps its own established lifecycle model (see Functional Requirement 17).
- Rewriting or relocating `CONTRIBUTING.md` — this specification requires the future Governance document to state the relationship between the two, not to absorb or supersede `CONTRIBUTING.md`'s content.

## Functional Requirements
The Governance document must contain the following sections, in this order:

1. **Title** — identifies the document as the Thrive OS Governance document.
2. **Metadata** — document identity fields (status, version, ratification date, owner, implements) consistent with other ratified Vault documents.
3. **Purpose of Governance** — states why this document exists: to operationalize the decision-making, review, approval, and amendment processes the Constitution's Article VI and Article VIII require, and how it relates to the Constitution, Vision, System Definition, Guiding Principles, and Architecture.
4. **Scope of Governance** — states what kinds of decisions and artifacts this document covers (proposal, review, approval, and amendment mechanics for Vault-governed artifacts) and what it does not (constitutional substance, aspiration, identity, judgment heuristics, technical design, or recurring operational procedure already owned by SOP).
5. **Relationship to the Constitution** — states that Governance is subordinate to and must never override or contradict the Constitution. Must include an explicit subsection or clearly delineated statement on **Relationship to Article VIII**, using authority-based wording equivalent to: Governance may operationalize constitutional procedures but may never modify, bypass, supersede, reinterpret, or diminish the constitutional authority established by Article VIII. Only an amendment enacted under Article VIII may alter Article VIII.
6. **Relationship to the Vision** — states that Governance must remain consistent with the Vision without restating its aspirational content; governance mechanics exist to serve decisions in the present, not to describe the future Thrive OS is building toward.
7. **Relationship to the System Definition** — states that Governance must not restate or extend the System Definition's Identity, Core Components, or System Boundaries; it may reference the Governance Hierarchy component but must not redefine it.
8. **Relationship to Guiding Principles** — states that Governance may be informed by Guiding Principles' heuristics when a decision-maker exercises discretion within a governance process, but Governance alone defines who decides, in what sequence, and under what procedure — Guiding Principles must never specify those mechanics.
9. **Relationship to Architecture** — states that Governance must not reference specific technologies, implementation patterns, or architectural components; where a governance mechanic touches Architecture (e.g. ADR approval), it is stated in terms of process, not technical content.
10. **Relationship to `CONTRIBUTING.md`** — explicitly distinguishes the scope of the two documents rather than establishing precedence between them: Governance governs Thrive OS as a governed system; `CONTRIBUTING.md` governs participation in the software repository. Must explain this scope distinction — what kind of thing each document governs — rather than stating which document prevails in the event of conflict.
11. **Governance Lifecycle** — defines the generalized proposal → review → approval → recording sequence that a decision affecting architecture, principles, or direction must follow, per Article VI.
12. **Decision Classification Framework** — defines categories of decisions (e.g. constitutional amendment, Foundation-document ratification, architectural decision, specification approval, routine implementation) and which level of the Governance Lifecycle each category must go through.
13. **Approval Model** — defines who may approve which category of decision, building on the Decision Classification Framework.
14. **Document Ownership Model** — defines the distinction (or lack thereof) between a document's Owner and its Approver across artifact types, resolving why Foundation documents currently record only an Owner while Specifications record both an Owner and an Approver.
15. **Role-to-Authority Mapping** — maps each of the Constitution's Article III roles (Founder, Chief Systems Architect, Lead Software Engineer, AI Roles) to the categories of decisions and document types each may approve, per the Decision Classification Framework and Approval Model.
16. **Change-Management Process** — defines how an already-ratified or already-approved document is amended: what distinguishes a deliberate amendment from a documentation-synchronization fix, and what triggers a version increment versus a new milestone.
17. **Artifact-Specific Lifecycle Models** — documents the distinct status vocabulary and transition rules already established for each artifact type, without unifying them into a single scheme: Foundation documents (`Draft → Ratified`), Specifications (`Draft → In Review → Approved → Superseded → Deprecated`), Architecture Decision Records (`Proposed → Accepted → Superseded`), and Projects (`Planned → Active → Paused → Complete → Cancelled`). For each, states who may move an artifact between states and what evidence or approval that transition requires.
18. **Non-Goals** — states what Governance explicitly does not cover, restating the boundary against Constitution, Vision, System Definition, Guiding Principles, Architecture, and `CONTRIBUTING.md` from the perspective of the document itself.
19. **Appendix — Definitions** — defines any terms introduced in Governance not already defined in the Constitution's, Vision's, System Definition's, or Guiding Principles' Appendices.

## Non-Functional Requirements
- **Procedural, obligation-bearing language:** unlike Guiding Principles, Governance describes mandatory mechanics and must use "must," "shall," and "may" precisely, consistent with the Constitution's normative style, since it operationalizes constitutional requirements rather than offering discretionary heuristics.
- **No constitutional substance:** the document must not state a rule that Thrive OS may never violate as if it were new constitutional content — any such statement belongs in the Constitution, subject to Article VIII amendment, not here; Governance only operationalizes what the Constitution already requires.
- **No artifact-vocabulary unification:** the document must preserve each artifact type's existing status vocabulary as documented in its respective template or precedent (Foundation documents, Specifications, ADRs, Projects) rather than introducing a single unified lifecycle scheme.
- **No implementation guidance:** the document must not reference specific code, file paths, schemas, configuration, or technology/vendor choices.
- **Vendor independence:** the document must remain technology-agnostic throughout.
- **Internal consistency:** the Governance Lifecycle, Decision Classification Framework, Approval Model, Document Ownership Model, Role-to-Authority Mapping, and Artifact-Specific Lifecycle Models must not contradict one another (e.g. a role granted approval authority in the Role-to-Authority Mapping must be consistent with the same role's authority as stated in the Approval Model).
- **Consistency with the Constitution, Vision, System Definition, and Guiding Principles:** no statement may contradict `01 Constitution/Constitution.md`, `02 Vision/Vision.md`, `03 System Definition/System Definition.md`, or `04 Guiding Principles/Guiding Principles.md`.
- **Standalone readability:** the document must be understandable without requiring the reader to first read Architecture documents or `CONTRIBUTING.md`.
- **Markdown standards:** the document must follow the Vault's existing Markdown conventions.

## Dependencies
- `01 Constitution/Constitution.md` (Ratified, v1.0.0) — satisfied.
- `02 Vision/Vision.md` (Ratified, v1.0.0) — satisfied.
- `03 System Definition/System Definition.md` (Ratified, v1.0.0) — satisfied.
- `04 Guiding Principles/Guiding Principles.md` (Ratified, v1.0.0) — satisfied.
- The top-level folder `vault/05 Governance/` already exists, per the Milestone 3B.5 Vault migration — satisfied.
- No Architecture document is required to exist before this specification can be approved; Governance's Relationship to Architecture section may be drafted against the existing `06 Architecture/README.md` placeholder.

## Risks
- **Constitutional self-reference:** if Governance's amendment mechanics could themselves be revised in a way that loosens Article VIII's substantive requirements, Governance would indirectly control its own constitutional constraint — mitigated by the explicit Functional Requirement 5 subsection stating Governance may never weaken or reinterpret Article VIII, and that only an Article VIII amendment can change Article VIII.
- **`CONTRIBUTING.md` duplication or conflict:** `CONTRIBUTING.md` already documents a work-flow sequence and role model that overlaps with what Governance will formally establish — mitigated by the mandatory Functional Requirement 10, which forces an explicit scope-distinction statement (Governance governs Thrive OS as a governed system; `CONTRIBUTING.md` governs participation in the software repository) rather than leaving the two to silently drift apart.
- **Status-vocabulary drift despite non-unification:** by design, this specification preserves four separate artifact-lifecycle vocabularies rather than unifying them (per your explicit instruction) — accepted as intentional, but it means future artifact types will each need their own lifecycle model added to Functional Requirement 17 rather than inheriting a shared one; this is a deliberate trade-off, not an oversight.
- **Role-mapping incompleteness:** Article III's "AI Roles" is the least concretely specified of the four roles — the Role-to-Authority Mapping (Functional Requirement 15) may need to be revisited once `11 AI Collaboration/`'s conventions document exists, since that document (not this one) is where Article VII's detailed AI collaboration conventions are meant to live.
- **Overlap with SOP at the Project-lifecycle boundary:** Artifact-Specific Lifecycle Models includes Projects, whose day-to-day operation is closer to SOP territory per `VAULT-IA-001`'s existing Governance/SOP distinction — mitigated by scoping Functional Requirement 17 to lifecycle *states and transition authority* only, not the operational procedures for running a Project day to day.

## Open Questions
None remaining. All items raised during the Milestone 3E architectural review have been resolved by explicit Functional Requirement:
- **`CONTRIBUTING.md` relationship:** resolved by Functional Requirement 10, mandatory.
- **Article VIII mechanics vs. substance:** resolved by Functional Requirement 5's explicit subsection.
- **Status-vocabulary unification:** resolved — explicitly rejected per your instruction; Functional Requirement 17 preserves artifact-specific models instead.
- **Article III role mapping:** resolved by Functional Requirement 15, mandatory.

## Deferred Decisions
- The exact wording of the Role-to-Authority Mapping for "AI Roles" may need refinement once an AI Collaboration Conventions document exists in `11 AI Collaboration/`; this specification does not block on that document's existence.
- Whether `CONTRIBUTING.md` is eventually trimmed, rewritten, or left as-is once Governance is ratified is left to a future decision following Functional Requirement 10's relationship statement — this specification only requires that relationship to be stated, not that `CONTRIBUTING.md` itself be changed.
- The exact list of terms requiring definition in the Appendix is left to implementation, provided every term introduced and used normatively is defined either there or by reference to an existing Constitution, Vision, System Definition, or Guiding Principles Appendix entry.

## Acceptance Criteria
- [ ] All nineteen required sections are present, in the specified order.
- [ ] The document explicitly states that Governance operationalizes the Constitution's Article VI and Article VIII requirements without restating constitutional substance.
- [ ] The Relationship to the Constitution section explicitly addresses Article VIII, stating Governance may never weaken or reinterpret constitutional requirements.
- [ ] The Relationship to `CONTRIBUTING.md` section explicitly distinguishes the scope of each document (Governance governs Thrive OS as a governed system; `CONTRIBUTING.md` governs participation in the software repository) without establishing precedence between them.
- [ ] The Artifact-Specific Lifecycle Models section documents Foundation, Specification, ADR, and Project lifecycles separately, without introducing a unified vocabulary.
- [ ] The Decision Classification Framework, Approval Model, Document Ownership Model, and Role-to-Authority Mapping are mutually consistent.
- [ ] No section defines Thrive OS's identity, boundaries, or components (System Definition content).
- [ ] No section states a judgment heuristic as if it were a governance mechanic (Guiding Principles content).
- [ ] No section references specific technology, implementation patterns, or vendor choices (Architecture content).
- [ ] No section contradicts the Constitution, the Vision, the System Definition, or Guiding Principles.
- [ ] The document reads as a complete, self-contained governance reference without needing external context to understand its intent.
- [ ] The rendered file passes Markdown formatting review (heading levels, list syntax, no broken links).

## Traceability
- Origin: Founder architectural discussion — Milestone 3E, following Milestone 3A (Constitutional Foundation), Milestone 3B (Vision), Milestone 3B.5 (Information Architecture Ratification & Repository Migration), Milestone 3C (System Definition), and Milestone 3D (Guiding Principles).
- Governing document(s): `01 Constitution/Constitution.md` (v1.0.0, Ratified); `02 Vision/Vision.md` (v1.0.0, Ratified); `03 System Definition/System Definition.md` (v1.0.0, Ratified); `04 Guiding Principles/Guiding Principles.md` (v1.0.0, Ratified); `VAULT-IA-001` (Ratified); `CLAUDE.md`; `CONTRIBUTING.md`.
- Implementation target: `vault/05 Governance/Governance.md`.
- Future ADR references: TBD.

## References
- [`vault/01 Constitution/Constitution.md`](../01%20Constitution/Constitution.md) — supreme governing reference this specification and the future Governance document must remain consistent with; source of the Article VI and Article VIII requirements this specification operationalizes.
- [`vault/02 Vision/Vision.md`](../02%20Vision/Vision.md) — aspirational reference this specification's future implementation must remain consistent with.
- [`vault/03 System Definition/System Definition.md`](../03%20System%20Definition/System%20Definition.md) — conceptual reference this specification's future implementation must not duplicate.
- [`vault/04 Guiding Principles/Guiding Principles.md`](../04%20Guiding%20Principles/Guiding%20Principles.md) — decision-heuristic reference this specification's future implementation must remain distinct from.
- [`vault/06 Architecture/Proposals/VAULT-IA-001 - Thrive Vault Information Architecture.md`](../06%20Architecture/Proposals/VAULT-IA-001%20-%20Thrive%20Vault%20Information%20Architecture.md) — ratified taxonomy establishing Governance as a distinct Foundation-layer domain and drawing its initial boundary against SOP.
- [`vault/05 Governance/README.md`](../05%20Governance/README.md) — current folder placeholder; implementation target's containing folder.
- [`vault/08 Specifications/SPEC-GP-001 - Guiding Principles.md`](SPEC-GP-001%20-%20Guiding%20Principles.md) — prior specification in this Documentation-First sequence, for structural precedent.
- [`CONTRIBUTING.md`](../../CONTRIBUTING.md) — repository workflow this specification requires the future Governance document to explicitly relate to.
- [`CLAUDE.md`](../../CLAUDE.md) — governing instructions for implementation work.
