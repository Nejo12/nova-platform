# Tattoo V1 — Consolidated Product Definition and M2 Closure Gate

**Status:** M2 Issue #17 — final **Founder-approval candidate**, not effective until this PR is manually merged  
**Issue:** [#17 — Finalize Tattoo V1 P0/P1/postponed scope and approve M2](https://github.com/Nejo12/nova-platform/issues/17)  
**Launch vertical:** Tattoo · independent artists  
**Approved product destination:** [canonical Tessnova Figma M2 definition](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=8-2)  
**Phase boundary:** This document commits **product scope**, not production architecture, code, provider choice or deployment. M3 begins **only when Founder manually merges this Issue #17 closure PR**. M4 does not begin just because M3 opens.

## 1. Authority, approval and research confidence

This is a **consolidation** of the individually Founder-merged Issue #11–#16, #28 and #29 contracts, with a new explicit **P0/P1/postponed classification** presented for final Founder approval. For detailed edge cases, the linked source contract remains authoritative; this summary must never weaken it.

| Decision / dependency | Authoritative approved M2 document |
| --- | --- |
| ICP, jobs, outcomes, measurements | [#11 — Tattoo ICP / JTBD / success](tattoo-v1-icp-jtbd-success.md) |
| Books, Flash, Custom Request semantics | [#12 — Tattoo domain semantics](tattoo-domain-semantics.md) and [glossary](tattoo-domain-glossary.md) |
| Public storefront, content priority, curated themes | [#13 — Storefront IA / themes](tattoo-storefront-ia-themes.md) |
| Deposit amount, financial states, 15-minute hold | [#14 — Deposit semantics](tattoo-deposit-semantics.md) |
| Onboarding, optional AI, publication/activation, Artist Home | [#15 — Onboarding and Artist Home](tattoo-onboarding-ai-artist-home.md) |
| Events second-vertical comparison / extraction result | [#16 — Events florist paper test](events-florist-paper-stress-test.md) |
| Public tattoo media publication authority | [#28 — Public media rights and permissions](tattoo-public-media-permission.md) |
| Initial language and locale | [#29 — German launch contract](tattoo-initial-language-locale.md) |
| Research limitations and unproven assumptions | [M1 synthesis](../validation/evidence-synthesis.md), [assumption register](assumptions.md) |
| Phase and development control | [M2 roadmap](../roadmap/M2-product-definition.md), [roadmap](../roadmap/roadmap.md), [AGENTS.md](../../AGENTS.md) |

**Evidence vs decision:** TAT-01/TAT-02 independently report social/Instagram-driven leads, repeated qualification, Books communication failure, manual deposits, Flash double-selling, and rejection of generic-looking pages. Detailed states, 15-minute hold, under-10-minute setup target, German-first UI, one authorized-image publication minimum and monetization constraints are **approved/proposed product policies or validation hypotheses**—not proven statistical findings. No claim of general market prevalence follows from two interviews.

**Founder M2 closure test:** Founder must approve this exact P0/P1/postponed scope, its hard invariants, research-risk register and phase-gated handoff. Prior individual issue merges alone did **not** constitute #17 approval. In particular, Issue #17's prior GitHub closure immediately after PR #31 was **reopened** because the required spec and phase gate were missing.

## 2. V1 customer, value and operating loop

**Primary ICP:** independent Tattoo artist, often solo/chair-renter, personally managing enquiries from Instagram/social/referrals and losing time to repetitive qualification, inconsistent Books visibility and/or scarce Flash reservations. The artist retains the customer relationship and control of Tattoo policies.

**Product thesis:** not a generic site builder and not a public appointment-booking marketplace. Tessnova creates a distinctive professional bio-link/storefront that turns social interest into **structured Custom Requests and safe Flash reservations**, then brings meaningful Tattoo work into a focused Artist Home.

```text
ARTIST: structured setup → legitimate work/identity → Books + optional Flash
       → explicit publish → one credible, shareable public page

CLIENT: public portfolio + accurate Books/Flash states
       → qualified Custom Request OR exclusive Flash hold/deposit

ARTIST: action queue → assess requests / manage Flash holds, reservations,
        accepted work and Deposits without invented appointment guarantees
```

### Product activation (not merely a public page)

An artist is activated only when **both** are true:
1. the artist considers their live bio link credible enough to represent their work; **and**
2. at least one real **Custom Request** or eligible **Flash** next-action path works.

An intentionally informational page with Books CLOSED and no claimable Flash may publish with truthful supporting navigation; it **does not count as activated**. Later Books closure does not erase historical first activation, but current actionability must be measured separately.

## 3. P0 — required Tattoo V1 product capabilities

**P0 means a functional product contract needed for Tattoo V1's bounded core loop.** It does **not** imply every optional route (e.g., Flash) must be configured by every artist; it implies that route must be safe when used. Actual sequencing, visual treatments, endpoints, vendors and code belong to M3/M4/M5.

### P0-A. Mobile-first public Tattoo presence

- One distinctive, mobile-first, artist-controlled shareable storefront, intended for a social bio link.
- Truthful first decision zone: **artist display name, city, primary tattoo style(s), visible Books status and context-dependent action**. Studio name only when applicable.
- Early prominent **authentic, artist-authorized portfolio media**, treated as work rather than generic stock or AI-generated artwork.
- Public sections: identity/status → real work → conditional Flash → artist/studio/style context → request/process/policies → appropriate repeated next action. Exact presentation varies by curated theme, **not** by state-truth changes.
- Curated visual presentation must materially differentiate composition, image rhythm, typography and density; **not** an open-ended freeform website/theme editor. Number of ready themes and precise styling are M3 design decisions; product cannot launch with a generic or misleading state treatment.
- Books OPEN: real Custom Request CTA. Books CLOSED: no new Custom Request CTA; visible status and optional truthful reopening note; separately AVAILABLE Flash remains accessible.
- Optional artist price floor/minimum and honest supporting/social links; never let social navigation substitute for the actual enabled Tattoo conversion flow when one exists.
- Respect mobile touch, keyboard/focus, legible state/CTA text and reduced motion in M3 designs.

### P0-B. Tattoo Books, not appointment availability

- Exactly two artist-controlled Books states: **OPEN** (accepting new Custom Requests) and **CLOSED** (not accepting them). Books **never** asserts appointment-slot availability.
- Books CLOSED disables **new** Custom Request submission **without invalidating or deleting existing** SUBMITTED/IN_REVIEW/NEEDS_INFO/ACCEPTED work.
- Books never automatically reopens from a date note, and never creates an implicit waitlist. Books does not govern individual Flash availability.

### P0-C. Custom Request qualification and assessment

Required client data per #12: **placement; approximate dimensions in cm; black/colour preference; one or more references; short idea/description; cover-up yes/no; rough desired timing/window; reply contact**. Cover-up detail is conditional where needed; **budget is optional**, not universally required.

Approved qualification states: **SUBMITTED → IN_REVIEW ↔ NEEDS_INFO → ACCEPTED or DECLINED**, with requester **WITHDRAWN** paths before acceptance as #12 specifies.

- **ACCEPTED** means willing to continue, **not** an appointment, date held, final quote, Deposit PAID or promised tattoo.
- Artist can triage and respond to qualification, request information, accept or decline within this bounded lifecycle.
- Client reference/cover-up images and messages remain **private**; do not silently reuse them as public portfolio.

### P0-D. Scarce Flash inventory and truthful claim path

Flash is **optional to publish** but the V1 Flash route must enforce:

```text
AVAILABLE → HOLD_PENDING_PAYMENT → RESERVED → BOOKED
           ↘ AVAILABLE (unpaid expiry / explicit release)
RESERVED/BOOKED → AVAILABLE only after artist's explicit release following
                  appropriate cancellation/financial disposition
```

- A Flash design represents **one scarce design**, **never two confirmed customers**.
- Only AVAILABLE may grant an exclusive hold; there is only **one active holder**.
- Working V1 hold is **15 minutes from acquisition**, fixed and not artist-configurable; this is an **M3-testable hypothesis**.
- Hold starts **before payment**. A successful deposit while the same client still owns an active hold creates **RESERVED**, **not BOOKED**.
- BOOKED requires a separately confirmed tattoo appointment; no public calendar is implied.
- Unpaid hold expiry returns to AVAILABLE; a **late-arriving payment never overrides another claim or produces another confirmed owner**.
- Reserved/Booked design cannot be shown as publicly claimable; cancellation **never auto-releases** confirmed scarce Flash.
- A Flash item requires eligible public media, truthful AVAILABLE state, a configured **positive fixed Flash Deposit with currency**, and applicable artist-owned refund/cancellation policy before a public paid claim is enabled.

### P0-E. Deposit money semantics separate from request/Flash state

- V1 **Deposit = fixed monetary prepayment toward specific tattoo work, credited to the final tattoo price**, not a non-crediting fee or percentage.
- Artist configures **separate default Custom and Flash amounts** where those routes are used; not one universal amount. Do **not** add arbitrary per-request overrides or percentages as universal P0.
- Custom Deposit is **optional per accepted request** and may be requested **only after Custom Request ACCEPTED**; payment does not itself book an appointment. Initial Custom-only publishing does **not** require a configured Custom Deposit.
- Flash paid public claim uses the active exclusive 15-minute hold; Deposit success and Flash reservation are distinct until the valid transition is confirmed.
- Financial states: **DUE → PAID → REFUNDED or RETAINED** as applicable. Payment failure isn't a new lasting state; late-payment exceptions require safe resolution. No partial-refund product contract in V1.
- Client sees exact amount/**actual currency**, work/artist association, credit toward final price, applicable policy and what is—and is not—being secured, **before payment**. Policy belongs to the artist, not an invented Tessnova-wide 24/48/72-hour rule.
- A cancelled paid work item requires clear financial disposition. Flash release after a confirmed reservation/booking is an **explicit artist action only after cancellation/Deposit disposition**, never an automatic side-effect.
- **Customer/merchant presentation remains artist-facing.** Payment-provider, identity and merchant-of-record solutions are **M4** choices subject to this contract.

### P0-F. Structured onboarding, publication and truthful activation

- Start a **private draft**; require display name, city, style(s), at least **one representative authentic public-work image with confirmed publication authority**, explicitly chosen Books state, truthful next action and preview.
- Draft Books may start **CLOSED as a safe proposed default**, but artist **must explicitly confirm** the selected status before public publish. M3 must test no-preselection versus this working default; do not create a third Books state.
- Artist explicitly publishes. Account creation, image upload, AI drafting and preview never auto-publish.
- No Flash, theme tuning, AI, generic policies or Custom Deposit setup blocker for a legitimate **Custom-only** fast path. Flash safety gates are conditional when the artist chooses to offer Flash.
- Books-CLOSED/no-Flash **informational** storefront is permitted with honest supporting navigation, but is not activation. A storefront lacking an authorized public work sample or any truthful next step cannot be marked ready.
- Artist may resume an incomplete private draft; replacing/updating published assets never bypasses permission checks.

### P0-G. Media rights, privacy and safe withdrawal

Issue #28's founder-approved risk-reduction product boundary:

- **Per publicly used portfolio/Flash asset**, affirmative unchecked-by-default artist acknowledgement of actual-file display rights and, for identifiable subjects, relevant person's-publication authority. An artist's assertion is **not independently verified client GDPR consent**.
- Keep “not sure,” unlicensed, disputed or rights-withdrawn assets **private/not publicly served**. Original Flash drawing versus an identifiable client photo requires different reasoning; no face does not guarantee anonymity.
- Restrict publication of high-risk minor/sensitive or intimate media pending separately approved specialist policy. Never repurpose private Custom Request references by default.
- Artist-initiated public removal plus a usable narrowly scoped concern/takedown path. Credible complaints trigger prompt restriction of affected media; M4/legal design handles actual takedown/erasure/retention.
- Loss of the last permitted portfolio image creates a publication-readiness problem and needs an honest existing-live fallback in M3. **Removing a public Flash image must not change its reservation/hold/Deposit states, auto-refund, auto-release or double-sell the design.**
- **Qualified independent legal review is a prerequisite before real public launch**, including GDPR roles, image/subject rights, policy/notice text and retention. This M2 product rule does **not** certify legal compliance.

### P0-H. Artist Home — Tattoo state and action hierarchy

A bounded professional work surface, not a CRM:

1. Public/draft status, link sharing, edit/preview, clear **Books** OPEN/CLOSED control.
2. Prioritized attention on **new requests**, requests needing review/clarification, **Flash active holds/expiry**, confirmation versus appointment distinctions, actionable accepted work/Deposit state, and payment/late-payment exceptions.
3. Actions on the **specific** Custom Request, Flash or Deposit record with truthful transition labels and clear customer/work association.
4. Privacy-aware rendering of client uploads. Do not show “booked appointment” for ACCEPTED or RESERVED alone.
5. Appropriate empty/error/exception states and accessibility for mobile-first operational use.

No full scheduling calendar, task suite, pipeline designer, campaign automation or generic multi-artist workspace.

### P0-I. German-first supported interface with true artist content

Founder-approved #29 product contract:

- Initial supported Tattoo system/interface language: **German** (`de`), with regional conventions from `de-DE` where appropriate, for **artist onboarding/Home, public storefront control labels, Custom Request, Flash/Deposit transaction flow, mandatory permission notices, system errors and support/transaction notices**.
- German domain explanations must distinguish Books from appointment availability and Flash HOLD from RESERVED from BOOKED.
- Artist- and client-authored text may remain in English/other languages without implying a translated site or alternate fully supported UI. No automatic translation of author text or legal terms.
- Deposit-enabled path must show understandable **artist-approved German cancellation/refund policy** before payment; an English-only artist policy cannot silently power a German paid Flash path.
- Sizes remain **cm**, amounts retain **artist-configured value and actual currency** (German formatting is not a silent EUR restriction), rough dates/windows remain non-appointments. Language-of-page/parts accessibility intent is mandatory.
- Exact legal German wording, support operations and implementation i18n choices require M3/M4/legal review.

### P0-J. Reliability and integrity outcomes

These are **product safety requirements**, not selection of production database/hosting techniques:

- No two Flash customers simultaneously confirmed for the same scarce design, even under simultaneous claims, expiry, retry and late payments.
- No client-reference media accidentally public, no unacknowledged portfolio/Flash media publicly eligible, no misleading public state.
- Requests already submitted survive Books closure; Books CLOSED still permits independent AVAILABLE Flash.
- Deposit amount, payment state, reservation state and appointment state are not conflated.
- Accessible, comprehensible German client decisions for money, permissions and actual action.

## 4. P1 — bounded, evidence-gated enhancements

**P1 does not mean automatically included in first alpha, before P0 safety works, or necessary to claim activation.** It is a candidate prioritized only when validation demonstrates value and Founder scopes the next issue.

| Candidate P1 | Why consider it | Why not P0 / trigger |
| --- | --- | --- |
| **Full English (`en`) platform interface** for both artist and client surfaces | International artists/visitors may be excluded by German-only UI | #29 established German-first; M3 tests real language comprehension and acquisition impact before committing a complete second-language contract. |
| **Optional AI factual-copy drafts** (bio, instructions, FAQ, SEO) | May improve speed or writing quality | #15 explicitly makes AI optional, human-reviewed, non-autonomous; no direct participant requirement or measured activation lift. Never invent claims/policies or publish automatically. |
| **Additional curated theme variations and bounded image/layout options** beyond the minimal credible launch compositions | Individuality matters; #13 requires composition-level differentiation | M3 decides count/quality and validates perceived uniqueness; do not turn into a freeform builder. |
| **Optional reopening date note / Guest Spot context** | Relevant to some working artists | #12 allows informative date/location notes without extra workspace, calendar or waitlist; not universal setup/publish blockers. |
| **Additional photo-permission helper / media credits ergonomics** | Artist confidence and rights transparency | #28 P0 gate and safe removal still mandatory; no release upload, consent CRM or automated legal attestation. |
| **Optional price-floor presentation / extra bio and process detail** | Some artists need minimum-price transparency | #13 supports these as artist-authored optional content; not universal minimum or dynamic quoting. |
| **Additional Artist Home prioritization refinements** | May reduce workflow friction for returning artists | Test #15 attention hierarchy with real tasks; no analytics suite or CRM expansion. |

**P1 versus already-permitted optional P0 content:** A simple price floor, optional reopening note or Guest Spot **may appear in V1 without being required for activation** if inexpensive and within the approved contract. This table classifies **enhanced controls and prioritization** as non-blocking P1, not a ban on the simple optional content #12/#13 already allowed.

## 5. Postponed / explicit V1 non-goals

These are **not authorized for Tattoo V1**, even if useful elsewhere, unless separately revisited with new evidence and Founder approval:

- Public appointment slot calendar / instant slot picker / all-in-one booking calendar / automatic Books reopening or waitlist.
- Generic CRM, marketing/newsletters, referral campaigns, automation rules, form builder or generic contact pipeline.
- Marketplace or public artist directory, cross-artist discovery marketplace.
- Multi-artist studio/organization workspace, role hierarchy and agency client-management features.
- Freeform drag-and-drop theme/page editor or “prompt to website” AI builder; generic AI agent for customer messages, policy or booking decisions.
- Generic multi-vertical business runtime, `vertical` schema discriminator, universal availability/booking/deposit/permission engine and speculative shared service/module extraction.
- Events/florist or Professional Speakers application features/code; #16 paper test did **not** prove a shared domain model.
- Custom domains as **universal P0**. One participant values this; universal need is not established. Reconsider in future only with evidence, not silent initial implementation.
- Carts/commerce catalog, proposal suite, contract generator/e-signature, detailed quote engine, VAT/invoicing suite.
- Percentage deposits, automatically generated refund windows, non-crediting reservation fees, partial refund rules and artist-configurable Flash hold duration without later explicit contract approval.
- Repeatable/unlimited Flash using the one-scarce-design invariant, social comments as a reservation authority, public preview of customer private references.
- Supported English (or more) system UI in **initial German-first P0**, partial bilingual claims, auto-locale translation, automatic legal-policy translation and unreviewed copy.
- Consent form/waiver collection suite, public media-rights verification engine or biometry/minor detection system. Actual legally required controls may be added only after specialist review and appropriate product approval.
- Advanced generalized analytics suite. Only the **specific #11 V1 validation metrics** are necessary; analytics architecture is M4, not a speculative dashboard.

**#20 Trigger B:** After and only after Founder-approved #17 merge, create a **separate** bounded `NOT_NOW.md` documentation PR reflecting this exact final list. Do not preempt it in #17 and do not close governance Issue #20.

## 6. Outcomes and validation criteria

Metrics use **Issue #11's operational definitions**, not inflated or newly invented market promises:

| Measure | Definition / success target | Evidence and next validation |
| --- | --- | --- |
| Usable bio link / activation time | Median **under 10 minutes** from starting setup to artist-accepted live link; activation also requires a working Custom/Flash action | **Hypothesis.** M3 task-based prototype timings and perceived credibility. |
| Qualified Custom Request readiness | At least **80%** of submitted requests assessable for basic suitability without first requesting missing mandatory information | **Validation target, not measured.** Run artist review scenarios, then later concierge/private beta. |
| Clarification burden | Median **at most 1** artist clarification message after structured request | **Validation target, not measured.** Compare with current DM friction rather than equating completion with usefulness. |
| Scarce Flash integrity | **Zero** double-confirmed customers for one design | **Hard invariant**, including concurrency, retries, expiry, late payment, cancellation/release and after media withdrawal. |
| First real external conversion | At least **one** actual external client completes a qualified request or valid Flash reservation during suitable validation | #11 conversion indicator; does not imply automated commercial launch during M3. |
| Retained work value | Repeat meaningful real Artist Home/Books/request/Flash/deposit activity after first activation | **No approved numeric retention threshold** yet; measure later against observed use. |
| Visual credibility | Artist would use public link instead of only Linktree/DM; clients can judge style/fit and next action | Research finding on importance, **unvalidated specific theme execution**; M3 qualitative/behavioral checks. |
| Safety / comprehension | Artist and client can distinguish OPEN/CLOSED, request acceptance, Flash hold, reservation, appointment and artist-facing Deposit | M3 task comprehension; M4 implementation risk analysis and eventual verified browser/data/payment tests. |
| German-first fit | German-speaking users understand all key flows; measure drop-off/confusion from English-preferring participants | #29 is an approved **scope choice**, not proof of language preference; escalate exclusion risk to Founder if material. |

Pricing remains a research hypothesis (TAT-01 indicates €19/month is plausible; TAT-02 around €20 decision point); **no universal subscription price, billing system or package tier is approved in M2**.

## 7. Explicit M3 design handoff — what becomes active after approval

**M3: Product Design**, beginning after Founder manual merge only:

1. Design lowest-fidelity complete **artist onboarding → preview → publish → share** with Custom-only and Flash-first variants; test one-image minimum, explicit Books confirmation and under-10-minute target.
2. Design public **mobile-first storefront** with compositionally distinct curated visual options that remain artist-centered; test credibility, work readability, CTA/state visibility and non-generic craft.
3. Design **Custom Request** required/optional/cover-up flows, needs-more-info loop, safe outcomes and privacy of client-uploaded references.
4. Design **Flash** race/hold/payment/reservation/appointment distinctions, timeout, retries, late-payment exceptions, and cancellation/release clarity.
5. Design **Deposit** policy/amount/artist relationship communication, accepted-work versus appointment, refund/retain resolution.
6. Design **Artist Home** priority surfaces, Books control, request triage, holds, Deposit exceptions and private-media access.
7. Design **per-asset media authority** and withdrawal/dispute/unready states, accessible rights report/contact route, and truthful published page after losing final authorized image. Legal wording remains separately reviewed.
8. Design **coherent German** labels/error/recovery/accessibility, with mixed-language artist/client-authored content examples. Test English-exclusion risk instead of claiming bilingual support.
9. Test optional/fast-path elements without quietly promoting AI, custom domains, generic themes or studio workspaces to P0.
10. Use **[M3 Issue #10](https://github.com/Nejo12/nova-platform/issues/10)** to study Tesnova.com's craft/motion/accessibility **without copying code, layouts, assets, copy or visual identity**.

Use existing [canonical Figma](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/) as design authority; add no unapproved production UI or Figma mutations under this documentation PR. Nova UI remains the source for **generic primitives**, Tattoo-specific UI stays in Tessnova.

**M3 acceptance evidence:** user-observed comprehension and task flow, distinct visual composition, no ambiguous Booking promises, sufficient edge/error states, accessibility/reduced-motion verification plans, prioritized defects and explicit Founder design reviews. A design exploration is not automatically canonical approval.

## 8. Unresolved M4 architecture and operational questions (explicitly **not decided**)

| M4 workstream | Question constrained by this approved product contract |
| --- | --- |
| Application structure | Which framework, routing, hosting, delivery environments and deployment workflow meet M3 design quality and Tattoo needs? |
| Data shape / transactional consistency | How to represent Books, Custom Request, scarce Flash, Deposit and appointment distinction **without** generic engines; how to enforce one active holder/customer atomically? |
| Payment architecture | Provider/merchant representation, artist ownership, currency support, payment confirmation, idempotency, webhook timing, refund/retain processing, late-payment resolution, cancellation financial state and reconciliation. |
| Hold/expiry reliability | Authoritative clock, transaction boundaries, races, expiry/retry, duplicate events, post-cancellation explicit artist release, no second paid confirmed owner. |
| Identity, authorization, privacy | Solo-artist control, legitimate requester access, private uploaded references/cover-up data, anti-leak permissions, retention/deletion, abuse protection and audit scope. |
| Media rights and hosting | Per-asset acknowledgement evidence, private-versus-public URLs, transformed variants/OG previews, metadata redaction, takedown, backup/CDN/indexing/erasure, incident escalation; qualified GDPR/photo-law review. |
| Legal/commercial obligations | Verified platform versus artist controller/processor and merchant roles; applicable German legal notices and client payment/policy language; consent and chargeback/dispute requirements. |
| Localization and accessibility | Complete German UX, BCP 47 page/parts semantics, public currency/number/date display without changing artist-set money, correct cm inputs, keyboard/reduced-motion, later `en` expansion feasibility. |
| Generic UI dependency | Which existing `@nova-component/ui` and `@nova-component/design-tokens` primitives can be consumed; Tattoo storefront themes and business controls remain local. |
| Test/CI/observability | Actual risk-based tests for no double-confirmation, request/Books rules, media privacy, payment exception recovery, browser UX and accessibility; **derive required CI gate names from actual stack** under #20, not sibling projects. |
| Production safety | Deployment isolation, operational response, complaint/takedown routing, monitoring and evidence collection needed before alpha/beta and real paid claims. |

M4 is **not automatically opened by completing M2**. M3 prototype validation may surface a **material product-contract conflict**; surface it to the Founder and revise via explicit issue/PR instead of silently broadening scope.

## 9. Founder approval, issue state and gates

**This PR has one and only one substantive Founder decision:** accept this consolidated **Tattoo V1 scope classification and M2 closure**. Individual #11–#16/#28/#29 semantics are not renegotiated here.

Founder review checklist:

- [ ] **P0** covers credible mobile storefront, scoped onboarding, Books, structured Custom Requests, optional-but-safe scarce Flash, distinct Deposit semantics, Artist Home, media/publication rights and **German-first UI**.
- [ ] **P1** is evidence-gated and nonblocking; AI, full English UI, extra themes/optional detail, media helpers are not invented launch prerequisites.
- [ ] **Postponed/non-goals** truly exclude public slot calendar, generic CRM/form/editor/vertical engines, multi-artist, marketplaces, Events code, auto-translation, generic payments/waiver systems and universal custom domain support.
- [ ] **Hard invariants** preserve zero double-confirmed Flash, request ≠ appointment, reserved ≠ booked, money ≠ schedule and private client references ≠ public portfolio.
- [ ] **Validation hypotheses** (<10 minutes, >=80% ready, <=1 clarification, retention TBD, language preference TBD) are not misrepresented as proven results.
- [ ] **M3** begins only upon merge, with Figma quality/accessibility work; **M4/M5 remain gated**, no production implementation in this PR.
- [ ] **#20 Trigger B** happens only **after** Founder merge and live verification, through a separate `NOT_NOW.md` PR.
- [ ] **Legal review** of media rights/privacy/payment terms is explicitly still needed before public operational launch.
- [ ] #17 must close via **this** approved PR, not because another PR's text happens to mention #17.

### Merge semantics

- **Before merge:** M2 ACTIVE; #17 OPEN; no production code; M3 not yet authorized.
- **Founder manually merges this exact final-scope PR:** that is the **explicit Founder M2 closure approval**. The accompanying M2 roadmap changes from ACTIVE to COMPLETE and M3 becomes the next active phase. #17 may then close.
- **After merge:** independently verify main merge SHA, issue closure, roadmap, changed files and any configured post-merge checks before proceeding.
- **Not authorized by merge:** M4 architecture approval, production implementation, automatic PR merges, changes to sibling repositories, Events application, or unrelated external-service mutations.

**READY FOR FOUNDER DECISION — NOT A MERGE BY AN AGENT.**
