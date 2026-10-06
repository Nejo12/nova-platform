# Tessnova Project Operating System

## Purpose

This document is the durable operating model for product, design, engineering and AI-agent work in `Nejo12/nova-platform`.

It complements `AGENTS.md`. If duplicated prose drifts, `AGENTS.md`, accepted ADRs and the current live roadmap govern agent behavior.

## 1. Mission

Tessnova exists to give independent professionals a profession-specific professional presence that converts attention into qualified business opportunities.

The approved first launch product is for independent tattoo artists.

V1 is not a generic website builder and not a generic multi-vertical platform.

## 2. Current strategic sequence

```text
M0 Foundation             COMPLETE
        ↓
M1 Market Validation      COMPLETE
        ↓
M2 Product Definition     ACTIVE
        ↓
M3 Product Design
        ↓
M4 Technical Architecture
        ↓
M5 MVP Alpha
        ↓
M6 Private Beta
        ↓
M7 Paid Beta
```

A later phase may not silently consume unresolved decisions from an earlier phase.

## 3. Decision ownership

The Founder owns final product, scope, brand, architecture-gate and merge decisions.

Agents may:
- research;
- analyze;
- recommend;
- draft;
- implement explicitly authorized scope;
- independently review evidence.

Agents may not:
- silently convert recommendations into Founder decisions;
- infer approval;
- merge;
- broaden phase scope.

When a decision is material and unresolved, create/identify a decision gate and stop.

## 4. Source-of-truth hierarchy

1. live GitHub `main`;
2. explicit Founder-approved decision;
3. accepted ADR/current roadmap/product specification;
4. canonical Figma for design behavior;
5. current issue;
6. implementation plan/PR;
7. executable code/tests;
8. summaries/handoffs/memory/external opinions.

Handoffs are navigation aids, never a substitute for checking live state.

## 5. Current accepted decisions

- brand: Tessnova;
- engineering repo: `nova-platform`;
- primary domain: `tessnova.de`;
- first launch vertical: Tattoo;
- second vertical stress test: Wedding / Events;
- later opportunity: Speakers;
- Nova UI remains domain-agnostic shared UI;
- Tesnova.com remains a permanent interaction-quality reference;
- production implementation is blocked until M2 closure is Founder-approved.

## 6. M2 execution order

Open M2 issues were established as:

- #11 — Tattoo ICP, JTBD and success metrics
- #12 — Books, Flash and Custom Request semantics
- #13 — storefront IA and themes
- #14 — deposit semantics / payment product boundary
- #15 — onboarding, AI assistance and Artist Home
- #16 — Events paper stress-test
- #17 — final P0/P1/postponed scope and M2 approval

Execute in this order unless live evidence gives a documented reason to adjust it.

Issue #10 is intentionally an M3 design-reference issue and should not be treated as M2 implementation work.

## 7. Product-definition laws

### Law 1 — Workflow over builder

The value proposition is not “build a prettier page.”

The current Tattoo wedge is:

```text
social discovery
→ Tessnova storefront
→ qualified custom request OR safe flash reservation
→ deposit/reservation state
→ artist home
```

### Law 2 — Tattoo semantics first

Use the customer's language:
- Books
- Flash
- Custom Request
- Deposit

Do not rename them into generic platform nouns prematurely.

### Law 3 — Different nouns can look similar without sharing a model

“Availability” differs across Tattoo, Events and Speakers.

Do not extract a shared object based on vocabulary alone.

### Law 4 — State that can lose money must have explicit semantics

Flash reservation integrity and deposit behavior require explicit product/state rules.

Do not hide money/reservation semantics in vague content configuration.

### Law 5 — Strong defaults beat builders

No form builder, generic rules engine or freeform theme system in V1 without new evidence.

### Law 6 — Artist owns the relationship

Tessnova should not unnecessarily make the customer feel they are booking “with the platform” instead of the artist.

Payment architecture must later respect this product requirement.

### Law 7 — Visual credibility is a functional requirement

Research participants rejected generic/template/AI-looking presentation.

Storefront design quality is part of conversion and trust.

## 8. Architecture extraction test

Before creating a reusable/shared module, prove a second real use case needs the same:

- data model;
- invariant;
- lifecycle/state machine;
- rendering contract;
- ownership/security semantics.

If not, keep it Tattoo-local.

## 9. Nova boundaries

### `nova-platform`

Owns Tessnova product logic, storefronts and vertical behavior.

### `nova-ui`

Owns reusable React primitives and semantic design tokens.

Published package names are:
- `@nova-component/ui`
- `@nova-component/design-tokens`

Product-specific design belongs to Tessnova unless reuse is proven.

### Klinnova / Slotnova

Separate products.

Do not use them as a dumping ground or borrow their domain models simply because they share the Nova family.

## 10. Design system / Figma

Figma is canonical for product design.

The Tessnova file contains:
- Cover / Index
- Brand
- Research
- Product Principles
- UX Flows
- Design Foundations
- Product
- Storefronts
- Prototypes
- Archive

Design work should preserve:
- accessibility;
- responsive behavior;
- reduced motion;
- keyboard/focus behavior;
- high visual craft;
- mobile storefront performance.

Tesnova.com is inspiration only.

## 11. Research governance

Use anonymized participant IDs.

Separate direct evidence from product interpretation.

Record contradictions rather than smoothing them away.

Do not require the original interview-count target if the current phase has already passed that gate, but continue to accept useful new evidence.

Prototype research should increasingly test concrete behavior/value rather than repeat broad discovery indefinitely.

## 12. Privacy / media

Do not commit participant private contact data.

Do not expose credentials.

Tattoo media can depict identifiable people/body areas. Product design must include a clear publication-permission acknowledgement before public display unless a later, stronger consent workflow is approved.

## 13. Deferred-product guardrail

Do not pull these into V1 simply because they are common SaaS features:

- public slot calendar;
- CRM;
- newsletters;
- generic form builder;
- multi-artist workspaces;
- marketplace/directory;
- freeform theme editor;
- proposal/contracts suite;
- generic analytics suite;
- generic vertical platform runtime.

Every addition must earn its place through evidence.

## 14. Agent / tool responsibilities

Use the tool best suited to the task, but keep one authority model.

### ChatGPT

Best for:
- orchestration;
- product/architecture reasoning;
- research;
- documentation;
- connected GitHub/Figma inspection;
- independent PR review;
- decision preparation.

### Claude Code on Founder's Mac

Preferred for authorized implementation that depends on:
- local Git/worktrees;
- Docker/Testcontainers;
- local repository verification;
- push/PR creation;
- complex implementation/debugging.

### Figma

Canonical design artifact.

### GitHub

Canonical requirements/status/ADR/review artifact.

## 15. PR / CI operating model

One bounded issue per PR by default.

After PR push:
- check exact-head CI once;
- if required jobs are still running, report pending and stop;
- no continuous polling.

Before Founder merge:
- independently review implementation;
- verify exact head/base;
- verify changed files;
- verify mergeability and auto-merge state;
- verify required exact-head CI;
- report READY FOR FOUNDER MERGE or DO NOT MERGE.

After Founder says merged:
- inspect live main;
- verify merge SHA;
- verify issue closure/parent state;
- verify required post-merge checks when applicable.

## 16. Recovery rule

Never throw away work because an agent session ended.

Recover actual state first, then continue only what remains.

## 17. Documentation-drift rule

When a durable decision changes, update the smallest set of source documents needed to prevent stale instructions from misleading future agents.

Do not leave a critical decision only in chat.

## 18. Change philosophy

Prefer:
- bounded changes;
- explicit state;
- evidence;
- boring infrastructure;
- rich product experience;
- reversible decisions until evidence requires commitment.

Avoid:
- architecture theater;
- premature extraction;
- framework decisions posing as product decisions;
- large “cleanup” PRs;
- AI-generated sameness.
