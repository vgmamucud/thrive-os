# Thrive OS Guiding Principles

## Status
Ratified

## Version
1.0.0

## Ratification Date
2026-07-02

## Owner
Founder

## Implements
SPEC-GP-001 (v1.0.0)

## Purpose of Guiding Principles
This document exists to provide decision heuristics for matters the Constitution intentionally leaves unsettled. The Constitution establishes Thrive OS's non-negotiable, amendment-gated commitments; it deliberately does not — and should not — prescribe a single course of action for every judgment call that arises in building and operating Thrive OS. Guiding Principles fills that space: it records what to weigh, prefer, or favor when a decision has no single constitutionally mandated answer, so that judgment is exercised consistently rather than re-derived from memory each time. It relates to the other Foundation and Engineering documents as follows: it is subordinate to the Constitution and may never override it; it is consistent with, but distinct from, the Vision's aspiration; it does not redefine what the System Definition already establishes; and it informs, without prescribing, how Governance processes and Architecture decisions are exercised in practice.

## Scope of Guiding Principles
This document covers recurring, non-constitutional judgment calls that require consistent reasoning across time and across collaborators — for example, how to weigh ambiguity in a specification, how to prioritize among competing legitimate considerations, or how to decide when a matter should be escalated rather than resolved independently. It does not cover matters the Constitution already settles, the procedural mechanics of how a decision gets approved, the conceptual identity or boundaries of Thrive OS, or any technology-specific engineering choice. A judgment call belongs here only if a reasonable collaborator, applying the Constitution and every other Foundation document in good faith, could still reach more than one defensible conclusion without further guidance.

## Relationship to the Constitution
Core Principles are authoritative constitutional commitments. Guiding Principles are decision heuristics that operate only where constitutional commitments do not prescribe a single course of action. Guiding Principles may never contradict, weaken, or reinterpret the Constitution. Where a guiding principle and a constitutional commitment appear to conflict in a given decision, the constitutional commitment governs and the guiding principle must be treated as inapplicable to that decision, not as a competing authority to be weighed against it.

## Guiding Principles

**Prefer clarity over cleverness when a specification is ambiguous.** Where a specification leaves more than one defensible reading, favor the interpretation a future reader — human or AI — could understand without needing to reconstruct the original reasoning. *Rationale: ambiguity resolved cleverly but silently compounds into confusion for the next collaborator; ambiguity resolved plainly is at least visible and correctable.*

**Favor the smallest change that satisfies an approved specification.** Weigh solving the stated problem over anticipating problems that have not yet been specified. *Rationale: speculative generality carries a real cost — more surface area to review, document, and maintain — and the Vault's Documentation-First discipline means genuine future needs will themselves become specifications when they arrive.*

**Weigh the Vault's recorded evidence over memory, intuition, or assumption.** When a decision depends on a fact about Thrive OS's current state, prefer checking the Vault over relying on recollection of a past conversation. *Rationale: this is the practical extension of the Constitution's Article IV source-of-truth commitment into everyday judgment — it should shape instinct, not just formal dispute resolution.*

**Prefer making an unresolved question explicit over resolving it silently.** When a decision could reasonably be deferred, favor recording it as an open or deferred question over picking an answer quietly to keep moving. *Rationale: a visible open question can be caught and corrected; a silent assumption embedded in an artifact usually cannot be, until it causes a problem downstream.*

**Favor traceable reasoning over efficient but unrecorded judgment.** When a non-trivial judgment call is made, prefer stating the reasoning briefly, even where a procedure does not require it, over leaving the outcome unexplained. *Rationale: traceability is what lets the next collaborator — human or AI — pick up work without re-deriving context, consistent with the Vision's success criteria.*

**Weigh explicit disagreement over silent compliance or silent override.** When an AI collaborator's recommendation and a human collaborator's judgment diverge on a matter the Constitution does not settle, favor surfacing the disagreement plainly over either party quietly deferring or quietly proceeding unchallenged. *Rationale: augmentation requires the disagreement to be visible; a system where either side silently yields loses the benefit of the other's judgment.*

**Prefer consistency with existing Vault precedent over local optimization.** When a new decision resembles one already made and recorded, favor following that precedent over choosing a locally better-looking alternative, unless the precedent itself is flagged as open or superseded. *Rationale: unexplained inconsistency between similar decisions is harder to justify later than a slightly suboptimal but consistent pattern, and consistency itself has compounding value across a long-lived system.*

**When guiding principles compete within a single decision, weigh the one more directly tied to the Constitution's Core Principles more heavily.** Not every principle here carries equal weight in every situation; where two pull in different directions, favor the one whose rationale traces most directly back to a constitutional commitment. *Rationale: these heuristics exist to serve the Constitution's purpose, not to become an independent source of competing authority among themselves.*

## Relationship to the Vision
Guiding Principles remains consistent with the Vision without restating its aspirational content. The Vision describes the future Thrive OS is intended to create; Guiding Principles describes how to reason in the present, in service of decisions that will move toward that future. Where a judgment call has a bearing on the Vision's success criteria — such as favoring traceable reasoning over unrecorded judgment — the connection is noted in this document's rationale, but the aspiration itself is never restated or elaborated here.

## Relationship to the System Definition
Guiding Principles does not restate or extend the System Definition's Identity, Core Components, or System Boundaries. It may reference a System Definition concept — such as Human-AI Collaboration — when a heuristic bears on it, but it does not redefine what that concept is or where its boundaries lie; those remain exclusively defined in the System Definition.

## Relationship to Governance
Guiding Principles may inform how a Governance process is exercised — for example, what a reviewer should weigh when judging whether a specification is ready for approval — but it never specifies who decides, in what sequence, or under what procedure. Any content describing decision steps, approval sequences, or amendment mechanics belongs exclusively to Governance, not to this document, regardless of how naturally it might otherwise fit alongside a related principle.

## Relationship to Architecture
Guiding Principles does not reference specific technologies, implementation patterns, or architectural components. Where a principle bears on engineering judgment — such as preferring the smallest change that satisfies a specification — it is stated abstractly enough to apply regardless of the technology in use, and any architecture-specific elaboration of that judgment belongs to Architecture or an Architecture Decision Record, not here.

## Non-Goals
Guiding Principles does not:
- Define or amend any constitutional rule, principle, or authority structure — those remain owned by the Constitution and change only through its Article VIII amendment procedure.
- Define decision-making process, review steps, or amendment mechanics — those belong to Governance.
- Define Thrive OS's conceptual identity, boundaries, or components — those belong to the System Definition.
- Reference specific technology, implementation patterns, or vendor choices — those belong to Architecture and Architecture Decision Records.
- Prescribe a single mandatory outcome for any judgment call — a heuristic informs reasoning; it does not replace it.

## Appendix — Definitions
- **Guiding Principles** — this document; the enduring set of decision heuristics that inform judgment on matters the Constitution's Core Principles do not settle, carrying no constitutional weight of its own.
- **Decision Heuristic** — guidance describing what to weigh, prefer, or favor when reasoning through a judgment call, as distinct from a rule (which mandates a single outcome) or a procedure (which specifies steps).
- **Judgment Call** — a decision for which the Constitution and the other Foundation documents do not prescribe a single course of action, leaving more than one defensible conclusion available to a reasonable collaborator.
