# M2 — Wedding / Events Florist Paper Stress-Test

**Status:** Issue #16 paper exercise — proposed for Founder approval  
**Issue:** #16  
**First launch vertical:** Tattoo (unchanged)  
**Second-vertical test subject:** Wedding / Events florist  
**Decision boundary:** This document classifies reuse risk. It does **not** approve Events V1, extract shared code, modify the Tattoo contract or authorize M3/M4 implementation.

## 1. Objective and authority

Question: **Which existing Tattoo V1 concepts remain useful for an Events florist without misnaming their work, weakening established invariants, introducing a generic booking/rules engine or inserting \`if (vertical)\` throughout the product?**

Sources:

- Direct evidence: [EVT-01 — Berlin/Brandenburg wedding florist](../validation/interviews/EVT-01.md); [EVT-02 — Hamburg wedding/event florist](../validation/interviews/EVT-02.md); [M1 synthesis](../validation/evidence-synthesis.md).
- Approved Tattoo baselines: [#11 customer/outcomes](tattoo-v1-icp-jtbd-success.md), [#12 domain semantics](tattoo-domain-semantics.md), [Tattoo glossary](tattoo-domain-glossary.md), [#13 storefront/themes](tattoo-storefront-ia-themes.md), [#14 deposits](tattoo-deposit-semantics.md), [#15 onboarding/AI/Artist Home](tattoo-onboarding-ai-artist-home.md).
- Governance: [AGENTS.md](../../AGENTS.md), [M2 roadmap](../roadmap/M2-product-definition.md), [project operating system](../governance/project-operating-system.md).
- Canonical Figma: [approved M2 product-definition frame](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=8-2). Tattoo-first, Events as paper stress-test; generic engines and production implementation deferred.

**Source-status vocabulary**

- **Observed (both):** independently described by EVT-01 and EVT-02.
- **Observed (single):** one interview only; not a universal Events rule.
- **Paper scenario:** illustrative, invented details to test boundaries; not participant evidence or product approval.
- **Inference / future candidate:** plausible contract worth testing later; no current extraction permission.
- **Approved Tattoo:** do not reopen via this paper exercise.

This exercise tests contract **shape and mismatch**, not Events demand, product-market fit, price, or implementation feasibility. Two Events interviews do not prove a universal florist workflow.

## 2. What Events research actually establishes

| Theme | EVT-01 | EVT-02 | Defensible conclusion |
| --- | --- | --- | --- |
| Acquisition | Instagram; planners; venue referrals; Google validates reputation | Instagram (~50%); venue recommendations (~30%); Google (~10%) | **Observed (both):** social/referral discovery and credible work presentation matter. |
| Qualification | Date, venue, guest count, ceremony/dinner scope, budget band; pictures helpful but moodboard **not mandatory** | Date, venue, guest count, budget range, style | **Observed (both):** date, venue, guest count and budget range/band are critical enquiry facts. Additional scope/style differs. |
| Price signalling | Starting prices, service area; exact lists private; minimum full install around €2,200 | “From €X”; budget is strongest qualifier | **Observed (both):** show enough starting-price context to reduce unsuitable budget enquiries, not full quote/pricing logic. |
| Availability | No public calendar desired; travel and installation can make a nominally free June Saturday infeasible | Manual calendar check; informal date holds ~one week | **Observed (both):** date enquiry needs manual operational assessment, not public instant appointment selection. **Single:** one-week informal hold. |
| Proposal drop-off | PDF sent after core enquiry facts; delay before call or quote loses leads | ~40% disappear after PDF, per participant report/attribution | **Observed (both):** later proposal/PDF process has friction. The reasons and percentages are not established population metrics. |
| Delivery context | Guest count and event scope change work and quote; no need for public contract flow yet | Contract and **30% bank-transfer deposit** follow proposal | **Single:** 30% deposit and contracts are EVT-02's current practice; neither a cross-Events standard nor permission to import Tattoo Deposit. |
| Visual standard | Rejects generic/obvious-AI look | Rejects template look | **Observed (both):** visual credibility is part of product value. |
| Team structure | Florist business; not enough evidence for team software | Studio team of two | **Single:** a two-person operation does not establish workspace/roles architecture. |

**Important Tattoo contrast:** the two Tattoo participants independently reported the hard operational failure of double-selling a scarce **Flash design**. Events participants described budget mismatch and operational date feasibility, **not** double-selling a uniquely numbered item that must be reserved with a 15-minute payment hold.

## 3. Florist paper example — separate from approved Tattoo product

### Paper-only storefront / enquiry loop

\`\`\`text
Instagram / venue / planner referral
    ↓
Florist-owned professional page
    ├─ authentic recent weddings / portfolio
    ├─ service area and relevant packages or service types
    ├─ transparent starting-price signal
    └─ clear "Enquire about your event" action
    ↓
Structured Events enquiry
    ├─ event date
    ├─ venue / location
    ├─ guest count
    ├─ budget band
    ├─ service scope or style context where needed
    └─ reply contact
    ↓
Florist manually assesses fit, logistics and feasibility
    ├─ request clarification / decline
    └─ continue conversation if promising
    ↓
Optional later call, PDF, proposal or contract (outside this test's MVP)
    ↓
Any deposit/payment only after future Events contract exists
\`\`\`

This is a **paper illustration**, not an approved Events application, requirements list or state machine. It intentionally avoids specifying public date availability, online booking, a contract generator, date-hold automation, or a payment provider.

### Example content structure

1. **Provider identity and geographic service area:** who is responsible, where they can realistically deliver/install work.
2. **Recent work / case studies:** wedding images, style, scale and context that demonstrate ability. An example case can be more persuasive than generic testimonials (EVT-01 observation).
3. **Packages or service scope:** bouquets, ceremony, dinner reception or fuller installation **when relevant**. These are commercial descriptions, **not** scarce Flash items.
4. **Starting price / minimum:** provider-supplied honest signal (e.g., “from…”); no automatic proposal computation.
5. **Enquiry action:** asks for date, venue, guest count, budget band and reply contact. Optional/conditional scope/style fields need later validation.
6. **Next steps:** human feasibility review before any promise or contract.

Portfolio image publication permission and private client-provided media require their own privacy boundaries. The separate Tattoo M2 media-permission decision remains unresolved; this document cannot impose its eventual legal mechanics on Events.

### Illustrative enquiry scenario A: plausible budget, uncertain feasibility

A couple enquires about a June Saturday at a venue outside the florist's usual service area, 85 guests and a budget band compatible with the florist's starting price. The enquiry is **not** accepted as a booking. Travel, installation time and commitments elsewhere may make it infeasible even if a simple calendar date has no recorded event. The florist evaluates manually and either continues, clarifies or declines.

The venue, date and guest count above are **paper test values**; no actual participant customer record is reproduced.

### Illustrative enquiry scenario B: revised scope

An initial enquiry is for 60 guests and ceremony flowers; later it becomes 100 guests plus dinner installations. The florist must reassess scope and price. A general “enquiry accepted” status must not freeze a quote or assume an appointment/contract. EVT-01 directly reported guest-count changes prompting quote revisions; the numerical example is illustrative.

### Illustrative enquiry scenario C: overlapping dates

Two couples enquire about the same Saturday. They may both be valid **enquiries** before any human commitment. Neither owns an exclusive design. A product cannot assign the first couple a Tattoo-style Flash hold or imply the second is automatically invalid: availability depends on resources, setup, logistics and the florist's commitments.

### Illustrative enquiry scenario D: informal date hold

EVT-02 reported holding dates informally for approximately a week. That **does not** establish an Events-wide hold-duration requirement, nor equivalence with the Tattoo 15-minute \`HOLD_PENDING_PAYMENT\` guarantee. A future Events commitment/hold contract would need its own trigger, expiry, exclusivity, cancellation and communication rules **if** validated.

### Illustrative enquiry scenario E: payment only later

EVT-02 reported a 30% bank-transfer deposit **after** proposal/contract. EVT-01 described deposits/contracts as later expansion value. This directly contradicts the idea of copying Tattoo's fixed monetary Deposit defaults or Flash paid-reservation state. The paper flow ends before payment. No Events payment lifecycle is approved here.

## 4. Compare the five extraction dimensions

The repo's extraction gate requires the **same** (1) data shape, (2) invariants, (3) lifecycle, (4) rendering/interaction needs and (5) ownership/security model in a **second real use case**, not mere similarity of names.

| Concept | Data shape | Invariants | Lifecycle | Interaction / rendering | Ownership / security | Decision |
| --- | --- | --- | --- | --- | --- | --- |
| Generic buttons, fields, typography, focus, responsive tokens | Primitive-level props can be domain-independent | Keyboard/touch/accessibility semantics shared | Component interaction only; no customer-workflow state | Generic primitives fit both; compositions diverge | Does not need Tattoo/Events business ownership | **Already reusable at UI-primitives level** through Nova UI, not new extraction. |
| Professional public presence / portfolio | Similar identity, images, text **at broad level**; Events service area/packages differ from Tattoo style/Books/Flash | Truthful media, public content control are broadly relevant; precise permission rules differ | Draft/publish can resemble, but Events readiness not approved | Both premium/visual; content order and actions diverge | Each professional owns public work; individual media rights/clients differ | **Future shared-contract candidate** only. |
| Structured enquiry | Common envelope (provider, requester, reply contact, submission) may emerge, but mandatory fields differ fundamentally | Must not promise acceptance/booking; qualification completeness is domain-specific | Tattoo #12 has approved SUBMITTED/IN_REVIEW/NEEDS_INFO/ACCEPTED/etc.; **no Events lifecycle approved** | Inputs and follow-ups differ; not a generic form builder | Private reference images vs private event logistics and budgets need distinct policies | **Future shared-envelope candidate**; keep domain-specific today. |
| Books status vs date feasibility | Tattoo OPEN/CLOSED intake status; Events date + venue + staffing/travel/setup context | Books never means public slots; Events date not instantly available | Books artist-controlled; Events requires assessment and potentially later manual commitments | Intake status display ≠ date feasibility enquiry | Artist intake vs florist operational capacity | **Not shared**; no generic availability engine. |
| Scarce Flash vs package / wedding date | Unique single-design inventory vs service scope and operational resources | Flash one confirmed customer hard invariant; no equivalent per-date one-customer rule demonstrated | Flash 15-min hold → RESERVED → BOOKED; Events holds unapproved | Flash claim/pay timer vs enquiry/consultation | Unique design ownership vs service commitments | **Not shared**; never map a date/package to Flash. |
| Tattoo Custom Request vs florist enquiry | Placement, centimetre size, colour, cover-up, required references vs date, venue, guests, budget band | Tattoo cannot accept without required qualification; Events budget/date/location critical | Events stages not approved | Both structured, but different screens, validation and copy | Different private client information | **Not shared as one domain model**; generic form controls may be reused. |
| Deposit/payment | Fixed per-Tattoo-work prepayment vs EVT-02 single example of percentage after contract | Tattoo credit to final price, Flash exclusive hold, refund/release invariants; Events unverified | Tattoo DUE → PAID → REFUNDED/RETAINED; Events state contract undefined | Tattoo Flash live hold/payment vs later proposal/contract payment | Client–artist relationship vs couples/organizer–florist and contractual parties (to validate) | **Not shared**; do not copy #14. |
| Onboarding / home | Identity + work appear in both; Tattoo needs Books, Flash, requests/deposits; Events needs scope, service area, enquiries | Tattoo must preserve #15 publish/activation and Flash safety; Events readiness unapproved | Similar UX phases possible; no common durable model approved | Artist Home is Tattoo-state-specific; florist attention model needs research | Tattoo solo artist; Events may be a team but evidence insufficient for roles | **Not shared as workflow**; reuse only existing generic controls. |
| Pricing information | Tattoo optional minimum; Events both emphasize starting price and budget fit | Must be accurate; no generic calculation contract | Quote/proposal timing differs | Optional Tattoo floor vs Events prominent starting-price guidance | Provider sets own public price and later quote | **Presentation principle only**, not pricing engine. |
| AI assistance | Both may need text; no Events AI evidence | #15 artist review and anti-fabrication apply to Tattoo; broader safety desirable | No Events approval flow defined | Optional drafting UI might reuse primitives | Client data disclosure and provider control differ | **No shared AI feature approved** by a paper resemblance. |

**Result:** no new domain-level shared abstraction meets the five-part extraction test. Nova UI's existing domain-agnostic primitives are the legitimate immediately reusable layer. Common publishing or enquiry envelopes are **hypotheses**, not extracted services/packages/fields.

## 5. Classification of reusability

### A. Truly generic foundations: use existing capabilities, do not extract new business models

- **Nova UI primitives/tokens/accessibility:** accessible buttons, input/control primitives, typography, focus semantics and responsive styling contracts where the existing library provides them. This is consumption of generic UI, not proof of identical Tattoo and Events product flows.
- **Cross-product quality principles:** accessible mobile presentation, factual provider-owned copy, usable image handling, unambiguous action labels, private/public separation, consent-aware display and safe error messages are constraints, **not** proof that a shared backend/media pipeline exists.
- **Generic infrastructure might eventually serve multiple apps:** hosting, operational monitoring, security, image delivery and identity concerns can be selected in M4 **for the actual Tattoo architecture**, not created now for Events. Their possible later reuse is not authorized by this paper test.

No assertion is made that non-UI infrastructure is already implemented.

### B. Future candidates requiring **real second-use-case** proof

- A **public-presence/publishing envelope** (provider-controlled live link, draft, public content), provided both businesses actually demonstrate the same security and publication contract.
- An **enquiry metadata envelope** (which provider received which private request and how to respond) **only after** validating separate domain rules and privacy/ownership needs. Tattoo Custom Request body and Events enquiry body remain separate.
- Public-asset/media consent workflows **only if** the separate legal/product decisions produce genuinely equivalent ownership and publication boundaries.
- Narrow UX controls for “from” price and galleries, as **presentation** rather than pricing/portfolio business engines.

Each candidate must be tested against the five dimensions when Events has its own approved real product contract and second actual implementation need. Even identical-looking components do not justify a shared domain schema.

### C. Must remain Tattoo-specific

- Books OPEN/CLOSED and any optional reopening/Guest Spot rules.
- Flash inventory, exclusive hold, 15-minute payment window, RESERVED/BOOKED transitions and the zero-double-confirmation invariant.
- Custom Request placement/size/colour/reference/cover-up/timing requirements, lifecycle and acceptance meaning.
- Fixed artist-defined Custom and Flash deposit defaults, work-specific credit, late-payment protection and Flash cancellation/release behavior.
- Tattoo storefront composition/curated themes; Tattoo activation measurements; Artist Home Books/request/hold/deposit priorities.
- Tattoo-specific AI source facts, copy boundaries and client-facing terminology.

**Do not rename these to \`Availability\`, \`Reservation\`, \`Job\` or \`Service\` simply to make a multi-vertical interface compile.**

### D. Must remain Events-specific if later approved

- Event **date + venue + operational fit** assessment and its context (travel/service area, setup, scheduling).
- Guest count, service scope, style and **budget band** qualification.
- Packages / services / recent full event case studies and starting-price fit.
- Any tentative date hold semantics, conflict rules and expiry *if evidence validates them*.
- Proposal/PDF/call/contract workflow *if separately scoped*.
- Percentage-based or contract-based deposits *if separately approved*.
- Any studio team/roles need *if separately validated*.

These are **illustrative future Events domain considerations**, not a committed Events V1 backlog.

## 6. Red-line thought experiments (what would break)

| Tempting generalization | Concrete failure | Required boundary |
| --- | --- | --- |
| Rename Books to universal Availability | “Open” could falsely imply a florist is free on a given date; Tattoo Books only enables Custom Request intake | Keep Tattoo Books status and event-specific feasibility enquiry separate. |
| Treat event dates as Flash items | An active 15-minute exclusive design hold blocks otherwise valid tentative enquiries; one customer/date rule is unjustified | No shared inventory/hold engine. |
| Reuse Tattoo Custom Request required fields | Florist receives size in cm/placement while date, venue and budget are missing | Build Events enquiries later from Events evidence, not a configurable generic form builder now. |
| Universal “deposit percent/fixed” flag | Flash confirmation could be detached from its active exclusive hold; Events contracts could be forced into Tattoo money state | Leave provider/model and Events deposit semantics undecided. |
| Reuse Tattoo Artist Home with labels swapped | Florist cannot triage guest-count scope changes or travel/logistics; Tattoo Flash integrity UI becomes noise | Keep distinct product dashboards if Events ever launches. |
| One generic package/gallery/Flash object | Packages are service offerings, often repeatable; Flash is one scarce artwork with a single customer | Separate content and reservation identities. |
| Treat published link as activation in all verticals | Tattoo #11 requires a working Custom or Flash path; informational-only pages do not qualify | Preserve Tattoo success definitions, test future Events outcomes independently. |
| Adopt an organization/workspace model because EVT-02 has two staff | Adds roles, permissions and tenancy complexity without repeated validation | Do not add a multi-artist or team engine. |
| Make AI generate event quotes/policies | Fabricates prices or contract commitments from incomplete scope | No Events AI approval; maintain Tattoo #15 review boundary. |

## 7. Boundaries around ownership, consent and client data

- **Tattoo:** the independent artist remains the customer-facing professional; client references/cover-up details are private; portfolio permission is an outstanding M2 closure issue.
- **Events:** the florist/business is the provider. An enquiry may contain couple/organizer contacts, venue, event date, guests, budget and private inspiration material. The interviews **do not** establish who may see/share these details or any team permission scheme.
- **Both:** do not publish private enquiry content as portfolio material; public photos may depict identifiable people and require a proper publication-permission decision at the appropriate phase.
- **Security model extraction:** “professional owns clients” is a directional principle, not a proved identical identity, tenancy, access-control or payment/legal-entity model.

This document introduces no person-level data, real client stories, private contact details or speculative legal implementation.

## 8. Research confidence and unanswered questions

**Repeated evidence (medium for direction, not quantified):** visual trust, social/referral discovery, mandatory date/venue/guest-count/budget qualification, price-floor guidance, manual availability checks, PDF/proposal friction.

**Single-participant evidence:** EVT-02's roughly one-week date holds, 30% bank-transfer deposit, team of two and estimated 40% PDF dropout; EVT-01's indicative price minimum/examples, travel-installation constraints and scope drift.

**Unknown:** unified Events lifecycle/status meanings; whether a tentative hold must be exclusive; if/when deposits matter to a future Events P0; viable florist ICP and pricing; specific permission/roles; exact landing-page IA, activation metrics, locale, scale and implementation needs.

**Future validation before any Events design/architecture:**

1. Can a florist qualify genuine fit with date, venue, guest count and budget band before a call?
2. Is a visible starting price sufficient to reduce low-fit enquiries without suppressing good ones?
3. What do “date available”, “tentatively held” and “confirmed” mean operationally across different florist sizes and service scopes?
4. Are two same-date events inherently incompatible, or is fit dependent on labor, travel and setup?
5. How are expanding guest count and service scope reflected in later estimates without misleading the client?
6. How does an Events customer understand the path enquiry → consultation/proposal → contract → any later deposit?
7. Do public event photos and private moodboards create permission/privacy patterns genuinely matching Tattoo needs?
8. Does a second real implementation actually share all five extraction dimensions, or only UI primitives?

These questions must not become requirements or tasks for Tattoo M3/M4 without new, relevant evidence.

## 9. Outcome for Tattoo M2 and #17

**Recommendation for Founder acceptance of this paper result:**

1. **Tattoo first remains the approved launch choice.** Nothing in Events evidence displaces the repeated Flash reservation-integrity problem or the narrow Tattoo V1 loop.
2. **No new shared domain layer qualifies now.** Product-specific first remains intact. Use Nova UI generic primitives as already intended; defer business extraction until a real second vertical independently proves the full contract.
3. **No changes** to #11–#15 Tattoo semantics, measurement targets or M3 validation hypotheses are necessary because of this paper test.
4. **Do not add Events to Tattoo V1 P0/P1**, and do not infer a new Events implementation phase from #16 approval.
5. Carry this **negative extraction result** into Issue #17's postponed/non-goal section and future architecture guardrails; no \`vertical\` schema field or generic availability/booking engine.
6. Preserve separate pending #17 prerequisites: Tattoo public-media permission rule and **initial locale** decision. These were not resolved by this Events stress test.

## 10. Explicit non-deliverables

Issue #16 does **not** create or approve:

- Events V1 specification, Events work tickets, Event pages, workflow states or implementation;
- a general product/vertical engine, \`vertical\` discriminator, generic availability/booking engine or service-schema generator;
- shared packages, components, databases, fields, tests or production code;
- modification of Nova UI, Klinnova, Slotnova or canonical Figma;
- a generic pricing/percentage-payment engine, contract builder, proposal automation or multi-user workspace;
- Tattoo requirement changes, Events payment architecture or an event date reservation algorithm.

Exact technical architecture remains M4, following explicit M2 closure through #17 and M3 Product Design.

## 11. Founder merge checklist — Issue #16 only

Merging this documentation PR signifies the Founder accepts that:

- [ ] EVT-01/EVT-02 evidence has been distinguished from illustrative assumptions and single-participant details.
- [ ] The florist paper loop includes portfolio/packages, date, venue, guests, budget, enquiry and **deposit later**.
- [ ] The five extraction criteria were applied to concrete Tattoo-versus-Events differences.
- [ ] Generic Nova UI presentation primitives remain the only immediately reusable established layer; possible common business envelopes are **not extracted**.
- [ ] Books, Flash, Custom Request, Tattoo Deposit and Artist Home remain Tattoo-specific.
- [ ] Events operational date feasibility, pricing/budget fit and proposal context remain distinct, tentative future considerations.
- [ ] No Events code, schema, shared package, \`vertical\` column, Figma mutation or M3/M4 work was performed.
- [ ] #17 still requires media-publication permission, locale and explicit Founder P0/P1/postponed approval before M2 can close.

**Approval scope:** Issue #16 paper-test classification only. Founder alone merges. This does not approve Events production, close M2 or authorize implementation.
