# Thrive OS Governance

## Status
Ratified

## Version
1.0.0

## Ratification Date
2026-07-02

## Owner
Founder

## Implements
SPEC-GOV-001 (v1.0.0)

## Purpose of Governance
This document operationalizes the decision-making, review, approval, and amendment processes the Constitution's Article VI and Article VIII require but do not themselves specify. Article VI states that decisions affecting Thrive OS's architecture, principles, or direction must be made deliberately and recorded, and that the process for doing so "shall be defined in a dedicated governance document." Article VIII states that constitutional amendments require explicit proposal, review, and approval, but does not state the forum or mechanics by which that happens. This document is that dedicated governance document: it defines who decides, in what sequence, under what authority, and with what artifact as the record, for every category of decision Thrive OS makes. It relates to the other Foundation and Engineering documents as follows: it is subordinate to the Constitution and operationalizes Article VI and Article VIII without altering either; it remains consistent with the Vision without restating its aspiration; it does not redefine what the System Definition already establishes; it may draw on Guiding Principles' heuristics when a decision-maker exercises discretion, without itself becoming a source of judgment guidance; and it governs how Architecture decisions are approved without describing Architecture's technical content.

## Scope of Governance
This document covers the proposal, review, approval, and amendment mechanics for Vault-governed artifacts and the decisions they represent: constitutional amendments, Foundation-document ratification, architectural decisions, specification approval, and the routine implementation work that flows from an already-approved specification. It does not cover the substance of any constitutional rule, the aspiration described by the Vision, the conceptual identity defined by the System Definition, the decision heuristics provided by Guiding Principles, the technical content of Architecture, or the recurring operational procedures for day-to-day work that belong to SOP. A governance mechanic answers "who decides this, and how is that decision recorded" — nothing else belongs here.

## Relationship to the Constitution
Governance is subordinate to the Constitution and must never override or contradict it. Every mechanic this document defines exists to operationalize a requirement the Constitution already states; none may introduce a new constitutional obligation.

**Relationship to Article VIII:** Governance may operationalize constitutional procedures but may never modify, bypass, supersede, reinterpret, or diminish the constitutional authority established by Article VIII. Only an amendment enacted under Article VIII may alter Article VIII. This document's Governance Lifecycle and Decision Classification Framework describe the forum, reviewers, and recording mechanics through which a constitutional amendment proposal moves — but the substantive requirements Article VIII itself imposes (explicit proposal, review against the system's purpose and principles, explicit approval, no amendment through silence or inference) remain fully intact regardless of anything stated elsewhere in this document.

## Relationship to the Vision
Governance remains consistent with the Vision without restating its aspirational content. The Vision describes the future Thrive OS is intended to create; Governance describes the mechanics by which decisions are made in the present, in service of reaching that future deliberately rather than by drift.

## Relationship to the System Definition
Governance does not restate or extend the System Definition's Identity, Core Components, or System Boundaries. It references the Governance Hierarchy component — the defined roles and their authority — but does not redefine it; that component's existence and its members remain exclusively defined in the System Definition and the Constitution's Article III.

## Relationship to Guiding Principles
Governance may be informed by Guiding Principles' heuristics when a decision-maker exercises discretion within a governance process — for example, weighing which interpretation of an ambiguous specification to approve. Governance alone defines who decides, in what sequence, and under what procedure; Guiding Principles never specifies those mechanics, and this document never restates a Guiding Principles heuristic as if it were a governance mechanic.

## Relationship to Architecture
Governance does not reference specific technologies, implementation patterns, or architectural components. Where a governance mechanic touches Architecture — such as how an Architecture Decision Record is accepted — it is stated in terms of process (who proposes, who accepts, what gets recorded), never in terms of the technical content an ADR or Architecture document might contain.

## Relationship to `CONTRIBUTING.md`
Governance and `CONTRIBUTING.md` differ in scope, not in precedence. Governance governs Thrive OS as a governed system: the decision-making, approval, and amendment mechanics that apply to Thrive OS's Foundation and Engineering artifacts, regardless of what repository or tooling happens to host them. `CONTRIBUTING.md` governs participation in the software repository: the day-to-day mechanics of contributing to this specific codebase — which template to copy, how commits are scoped, how the Vault's structure maps onto file paths. A contributor follows `CONTRIBUTING.md` to know where to put a file and how to phrase a commit message; the same contributor follows Governance to know who must approve the decision that file records. The two are complementary descriptions of different kinds of thing, not competing authorities over the same kind of thing.

## Governance Lifecycle
A decision affecting Thrive OS's architecture, principles, or direction must move through the following sequence, per Article VI:

1. **Proposal.** The decision is stated explicitly, in writing, in the Vault artifact type appropriate to its Decision Classification (see below). A decision is never inferred from silence or assumed from prior conversation.
2. **Review.** The proposal is reviewed for consistency against the Constitution, the Vision, and every other Foundation document it touches, by the role or roles the Approval Model designates for its Decision Classification.
3. **Approval.** An explicit approval is recorded by the authority the Approval Model designates for that Decision Classification. No decision takes effect through silence, inference, or informal agreement.
4. **Recording.** The approved decision is captured durably in the Vault artifact itself — through status and version metadata, a Changelog entry, or an Architecture Decision Record — so that it remains traceable to an approved document rather than to memory, per Article IV.

Every category of decision this document classifies moves through all four stages; what differs by category is who performs Review and Approval, and how much ceremony each stage carries.

## Decision Classification Framework
Every decision Thrive OS makes falls into exactly one of the following categories:

- **A — Constitutional Amendment.** Any change to `01 Constitution/Constitution.md` itself.
- **B — Foundation Document Ratification or Amendment.** The initial ratification or a subsequent substantive revision of the Vision, the System Definition, Guiding Principles, or this Governance document.
- **C — Architectural Decision.** A decision recorded as an Architecture Decision Record or a change to the current, as-built Architecture.
- **D — Specification Approval.** The initial approval or a subsequent substantive revision of a Specification governing future implementation.
- **E — Routine Implementation.** Work that builds against an already-approved Specification and Architecture without changing any prior decision.

A decision belongs to the category matching what it changes, not the artifact type that happens to record it — for example, a Specification revision that only fixes a stale cross-reference is a documentation-synchronization fix (see Change-Management Process), not a Category D decision.

## Approval Model
Each Decision Classification requires the following Review and Approval authority:

- **A — Constitutional Amendment:** reviewed against the system's purpose and principles by the Chief Systems Architect where architectural impact is present; approved solely by the Founder, consistent with the Founder's final authority over Thrive OS's direction (Article III) and Article VIII's explicit-approval requirement.
- **B — Foundation Document Ratification or Amendment:** reviewed by the Chief Systems Architect for consistency with existing Foundation documents; approved solely by the Founder, consistent with the precedent already set by the Constitution, the Vision, the System Definition, and Guiding Principles, each ratified by the Founder.
- **C — Architectural Decision:** proposed and reviewed by the Chief Systems Architect, who holds architectural stewardship per Article III; approved by the Chief Systems Architect, subject to the Founder's retained authority to override any architectural decision.
- **D — Specification Approval:** drafted by the Lead Software Engineer or the Founder; reviewed by the Chief Systems Architect for architectural consistency; approved solely by the Founder, consistent with the precedent set by every Specification ratified so far.
- **E — Routine Implementation:** executed by the Lead Software Engineer, or by an AI Role acting under the Lead Software Engineer's or Founder's delegated authority, within the bounds of an already-approved Specification and Architecture; no separate approval step is required beyond the Specification and Architecture that already govern it.

## Document Ownership Model
Every Vault artifact records an **Owner**: the role accountable for drafting the artifact and keeping it current. Where an artifact's Decision Classification designates a single role as both drafter and sole approval authority — as Classification B does, where the Founder is both Owner and the only role empowered to ratify — the artifact records only an Owner, and ratification is understood to require that Owner's explicit approval; recording a separate Approver field would be redundant. Where an artifact's Decision Classification separates drafting from approval authority — as Classification D does, where the Lead Software Engineer or Founder may draft but only the Founder may approve — the artifact records both an Owner and a separate **Approver**, so the two roles remain distinguishable even when the same individual happens to occupy both.

## Role-to-Authority Mapping
Mapping the Constitution's Article III roles to the Decision Classification Framework and Approval Model:

- **Founder** — sole approval authority for Classification A (Constitutional Amendment) and Classification B (Foundation Document Ratification or Amendment); sole approval authority for Classification D (Specification Approval); retains authority to override any Classification C (Architectural Decision) approved by the Chief Systems Architect, consistent with the Founder's final authority over Thrive OS's direction.
- **Chief Systems Architect** — proposes and approves Classification C (Architectural Decision) as architectural steward; reviews Classification A and B proposals for architectural impact; reviews Classification D proposals for architectural consistency before Founder approval.
- **Lead Software Engineer** — drafts Classification D (Specification) proposals; executes Classification E (Routine Implementation); may recommend improvements to any classification but holds no approval authority over Classifications A, B, C, or D, consistent with the Decision Boundaries already established for implementation work.
- **AI Roles** — may draft, implement, and recommend within any Decision Classification when explicitly delegated by a human role holding authority for that classification, per Article VII; may directly execute Classification E under delegated authority; may never hold final approval authority for Classifications A, B, C, or D, consistent with the Constitution's requirement that AI augment human judgment without substituting for it.

## Change-Management Process
An already-ratified or already-approved document may be changed in one of two ways:

- **A deliberate amendment** changes the substance of a decision the document already records — for example, revising what a Guiding Principle instructs, changing a Specification's Functional Requirements, or altering a constitutional Article. A deliberate amendment must move through the full Governance Lifecycle for the artifact's Decision Classification again, and must increment the artifact's version according to its own template convention.
- **A documentation-synchronization fix** corrects a document to accurately reflect a decision that has already been approved elsewhere but is not yet reflected in the document's text — for example, updating a cross-reference after a folder migration, or removing a stale "pending approval" note once approval has occurred. A documentation-synchronization fix does not require re-running the Governance Lifecycle, but it must still be recorded (for example, in `CHANGELOG.md` or the artifact's own history) and must never alter the substance of any decision the document records.

Introducing an entirely new instance of a Decision Classification — such as a new Foundation-layer domain — is a Classification B decision in its own right (as `VAULT-IA-001` was) and constitutes a new milestone rather than a version increment to an existing document.

## Artifact-Specific Lifecycle Models
Each artifact type retains its own established status vocabulary; none are unified into a single scheme.

- **Foundation documents** (`Draft → Ratified`): only the Founder may move a Foundation document from `Draft` to `Ratified`, and only once the document satisfies every Acceptance Criterion in its governing Specification.
- **Specifications** (`Draft → In Review → Approved → Superseded → Deprecated`): the Owner moves a Specification from `Draft` to `In Review` by requesting review; the Founder moves it from `In Review` to `Approved`; a later Specification addressing the same subject may move an earlier one to `Superseded`; the Founder may mark a Specification `Deprecated` once it no longer governs active implementation.
- **Architecture Decision Records** (`Proposed → Accepted → Superseded`): the Chief Systems Architect proposes an ADR; the Chief Systems Architect accepts it, subject to the Founder's override authority under Classification C; a later ADR addressing the same decision may move an earlier one to `Superseded`.
- **Projects** (`Planned → Active → Paused → Complete → Cancelled`): the Project's Owner may move it between `Planned`, `Active`, `Paused`, and `Complete` as work progresses; moving a Project to `Cancelled` requires the Founder's approval, since cancellation abandons previously committed scope.

## Non-Goals
Governance does not:
- Define or amend any constitutional rule, principle, or authority structure — those remain owned by the Constitution and change only through its Article VIII amendment procedure.
- Restate the Vision's aspiration, the System Definition's identity content, or Guiding Principles' decision heuristics.
- Define Thrive OS's conceptual identity, boundaries, or components — those belong to the System Definition.
- Reference specific technology, implementation patterns, or vendor choices — those belong to Architecture and Architecture Decision Records.
- Unify the Foundation, Specification, ADR, and Project status vocabularies into a single scheme — each retains its own artifact-specific lifecycle model.
- Establish precedence over `CONTRIBUTING.md` — the two documents govern different kinds of thing, per their stated scope distinction.
- Describe the recurring operational procedures for day-to-day work — those belong to SOP.

## Appendix — Definitions
- **Governance** — this document; the operationalization of the Constitution's Article VI and Article VIII requirements, defining who decides, in what sequence, and under what authority, for every category of decision Thrive OS makes.
- **Governance Lifecycle** — the Proposal → Review → Approval → Recording sequence every Decision Classification must move through.
- **Decision Classification** — one of the five categories (Constitutional Amendment, Foundation Document Ratification or Amendment, Architectural Decision, Specification Approval, Routine Implementation) every Thrive OS decision falls into.
- **Approver** — the role holding final authority to approve a given artifact, as distinguished from its Owner where the Document Ownership Model separates the two.
- **Deliberate Amendment** — a change to an already-ratified or already-approved document that alters the substance of a decision it records, requiring the full Governance Lifecycle to be repeated.
- **Documentation-Synchronization Fix** — a change to a document that corrects it to reflect a decision already approved elsewhere, without altering the substance of any decision.
