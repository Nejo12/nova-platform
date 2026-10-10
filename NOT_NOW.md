# NOT NOW — Tessnova Tattoo V1 Scope Guardrail

**Status:** Approved M2 scope boundary; established after Founder-approved Issue #17 closure  
**Source of truth:** [Tattoo V1 consolidated P0/P1/postponed specification](docs/product/tattoo-v1-approved-scope.md), especially [§5 — Postponed / explicit V1 non-goals](docs/product/tattoo-v1-approved-scope.md#5-postponed--explicit-v1-non-goals)  
**Governance trigger:** [Issue #20, Trigger B](https://github.com/Nejo12/nova-platform/issues/20)  
**Phase:** M0–M3 complete. M4 Technical Architecture planning is active (Founder 2026-10-10). Production implementation and M5 remain gated.

## Rule

**These items are not authorized for Tattoo V1.** Do not introduce them through design exploration, implementation tickets, opportunistic abstractions, dependencies or “small” improvements. Revisit only with new relevant evidence and **explicit Founder approval through a separate bounded issue/PR**.

This file records **the existing approved exclusions**. It does not invent new product decisions, delete already-approved P0 behavior, remove optional supported content, or permanently ban later verticals.

## Postponed / explicit Tattoo V1 non-goals

The following list is taken from the approved Issue #17 final specification.

1. **Public calendar and waitlist:** Public appointment slot calendar, instant slot picker, all-in-one booking calendar, automatic Books reopening or waitlist.
2. **Generic CRM and outreach:** Generic CRM, marketing/newsletters, referral campaigns, automation rules, form builder or generic contact pipeline.
3. **Marketplace:** Marketplace or public artist directory, cross-artist discovery marketplace.
4. **Multi-artist tenancy:** Multi-artist studio/organization workspace, role hierarchy and agency client-management features.
5. **Freeform builder / autonomous AI:** Freeform drag-and-drop theme/page editor or “prompt to website” AI builder; generic AI agent for customer messages, policy or booking decisions.
6. **Generic vertical/runtime abstraction:** Generic multi-vertical business runtime, `vertical` schema discriminator, universal availability/booking/deposit/permission engine and speculative shared service/module extraction.
7. **Other-vertical product code:** Events/florist or Professional Speakers application features/code; #16 paper test did **not** prove a shared domain model.
8. **Universal custom domains:** Custom domains as **universal P0**. One participant values this; universal need is not established. Reconsider in future only with evidence, not silent initial implementation.
9. **Extended commerce / proposals:** Carts/commerce catalog, proposal suite, contract generator/e-signature, detailed quote engine, VAT/invoicing suite.
10. **Unapproved payment variants:** Percentage deposits, automatically generated refund windows, non-crediting reservation fees, partial refund rules and artist-configurable Flash hold duration without later explicit contract approval.
11. **Contradictory Flash / privacy shortcuts:** Repeatable/unlimited Flash using the one-scarce-design invariant, social comments as a reservation authority, public preview of customer private references.
12. **Unapproved language scope:** Supported English (or more) system UI in **initial German-first P0**, partial bilingual claims, auto-locale translation, automatic legal-policy translation and unreviewed copy.
13. **General consent/verification tooling:** Consent form/waiver collection suite, public media-rights verification engine or biometry/minor detection system. Actual legally required controls may be added only after specialist review and appropriate product approval.
14. **Generic analytics suite:** Advanced generalized analytics suite. Only the **specific #11 V1 validation metrics** are necessary; analytics architecture is M4, not a speculative dashboard.

## Do not confuse exclusions with approved Tattoo V1

This document must **not** be used to block the actual bounded Tattoo workflow defined in [approved M2 scope](docs/product/tattoo-v1-approved-scope.md):

- **Books OPEN/CLOSED** denotes Custom Request intake and is **not** a public slot calendar.
- **Custom Request** collects tattoo-specific qualification; ACCEPTED does **not** create an appointment.
- **Flash** is optional for an artist to publish, but the available paid-claim path requires a single exclusive 15-minute hold and no double-confirmation.
- **Deposit** is an artist-defined fixed credited prepayment attached to specific accepted Custom work or a specific Flash design; it is **not** a generic pricing, payments or refund engine.
- **Storefront** is one distinctive, mobile-first, curated presentation—not a freeform site builder. Optional price floor, short reopening note, Guest Spot and supporting links remain permissible **only within their approved #12/#13 bounds**; their existence does not authorize expanded systems.
- **Portfolio and Flash media** require per-public-asset publication authority, with private Custom Request references kept private. Safe public removal/takedown is P0; a consent-form suite is not.
- **German-first interface** is the supported initial P0 system UI; an artist may author English or other-language biography/portfolio text without Tessnova claiming a complete translated client flow.
- **Artist Home** is Tattoo work triage and state actions—not a CRM, calendar or analytics suite.
- **Optional AI drafting and full English support** are evidence-gated **P1 candidates**, not covert P0 promises or excuses to build autonomous tools.
- **Nova UI** owns generic primitives/tokens; Tessnova owns Tattoo-specific UI/semantics. The Events paper stress test does not approve new shared domain packages.

A P1 candidate is **not** an approved implementation instruction. A postponed capability requires its own Founder decision; do not relabel it P1 to evade this guardrail.

## Phase and change control

1. **M3:** Canonical [Tessnova Figma](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/) remains source of truth for approved Tattoo visual/interaction design. [Issue #10](https://github.com/Nejo12/nova-platform/issues/10) is a closed visual-craft reference record, not permission to copy Tesnova.com.
2. **M4:** Architecture planning is Founder-authorized as of 2026-10-10. CI/payment/security **decisions** still require documented review and Founder approval. No production implementation automatically follows from M3 closure or from opening M4.
3. **M5:** MVP Alpha implementation remains separately gated. No agent or PR may bypass Founder-controlled approvals.
4. **Issue #20:** Trigger B is satisfied when this file is Founder-merged. **Leave Issue #20 open** for Trigger C (real CI/ruleset in M4), D (pre-M5 governance), E (collaborators/CODEOWNERS), and F (ADR index when complexity warrants it).
5. **Changes to scope:** Cite new evidence, state the exact affected approved contract, create/identify a bounded issue, request explicit Founder approval and update this file and the authoritative spec through a reviewed PR. Never silently reconcile a conflict or infer approval from a chat, branch or agent report.
6. **Merges:** Founder only. Never auto-merge, merge on Founder's behalf or push directly to `main`.

## Developer/agent quick check

Before adding a feature or abstraction, check:

- Is it explicitly within [M2-approved Tattoo P0](docs/product/tattoo-v1-approved-scope.md#3-p0--required-tattoo-v1-product-capabilities) or a separately Founder-authorized later scope?
- Is it on the excluded list above, or a disguised equivalent using generic terminology?
- Does it weaken Books, scarce Flash, Custom Request, Deposit, media or locale contracts?
- Is the work in an active authorized phase and bounded issue/PR?
- Has Founder approval been obtained for any material scope change?

If an answer reveals a conflict, **stop and surface it**. This file is a guardrail, not an authority to choose new architecture or implementation.

**No new feature, system or CI requirement is approved by this document.**
