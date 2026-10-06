# Tattoo V1 — Product Hypothesis

**Status:** M2 working hypothesis — not yet approved V1 specification

Issue #11 customer/outcome definition:
`docs/product/tattoo-v1-icp-jtbd-success.md`

Issue #12 domain-semantics definition:
`docs/product/tattoo-domain-semantics.md`

Issue #13 storefront IA/theme definition:
`docs/product/tattoo-storefront-ia-themes.md`

Issue #14 deposit-semantics definition:
`docs/product/tattoo-deposit-semantics.md`

Issue #15 onboarding, bounded AI and Artist Home definition:
`docs/product/tattoo-onboarding-ai-artist-home.md`

## Target customer hypothesis

Primary ICP:

**Independent tattoo artists who own the client relationship, receive meaningful inbound interest through Instagram/social/referrals, and still qualify/manage that demand through fragmented manual tools.**

Typical fit includes:

- solo independent artists and chair renters;
- enquiry handling through DMs/email/WhatsApp;
- manual qualification around placement, size, references and related details;
- artist-controlled Books status and client communication;
- manual deposit handling;
- desire for a distinctive professional presence rather than a generic template.

Artists who also sell scarce flash are a particularly strong early-adopter signal because reservation integrity is a repeated high-severity pain, but Flash is not mandatory for every V1 customer.

Multi-artist studio/team management, marketplace-first buyers, and full public-calendar buyers are outside the primary V1 ICP.

See `docs/product/tattoo-v1-icp-jtbd-success.md` for the evidence, explicit exclusions and M3 validation assumptions.

## Core customer job

**Turn social attention into qualified tattoo work without losing serious enquiries, repeating the same questions, or double-selling scarce flash.**

Top jobs are:

1. convert social discovery into a credible next action;
2. qualify custom tattoo demand before manual conversation;
3. keep serious enquiries out of social inbox noise;
4. reserve scarce flash without double-confirming it;
5. tie commitment to the specific request/design while preserving the artist-owned customer relationship.

## Candidate P0 areas

### Public storefront

Proposed #13 definition for Founder review:

- one-page, mobile-first artist storefront linked from Instagram/social;
- first decision zone: artist identity, city/studio context, styles, Books state and correct next action;
- portfolio appears early as the primary credibility/fit surface;
- Flash is a separate conditional scarce-inventory section, not ordinary portfolio content;
- artist/style/studio context supports trust after the work is visible;
- process/policies/booking instructions prepare the client before requesting;
- final action repeats the correct next step without routing serious demand back into ambiguous DMs;
- price minimum/floor remains optional;
- Books Closed disables new Custom Request intake but does not suppress independently Available Flash.

Theme contract:

- themes share the same Tattoo semantics/data;
- themes must vary composition, density, typography and image treatment—not only colour;
- state truth always outranks aesthetics;
- V1 uses curated structured themes, not a freeform page builder;
- final visual design, theme count and motion language remain M3.

See `docs/product/tattoo-storefront-ia-themes.md` for the full IA, content matrix, theme rules and mobile-first constraints.

### Books

Founder-approved #12 definition:

- OPEN = accepting new Custom Requests;
- CLOSED = not accepting new Custom Requests;
- Books is not a calendar and does not promise appointment slots;
- existing submitted requests remain active when Books close;
- Flash availability is independent from Books;
- optional future-opening information is informational only;
- Guest Spot is contextual/datestamped information, not a separate workspace/location engine.

### Custom Request

Required V1 qualification information:

- placement;
- size in centimetres;
- black / colour preference;
- one or more reference images;
- short description / idea;
- cover-up status;
- rough desired timing;
- reply contact.

Budget remains optional.

Founder-approved #12 lifecycle:

`SUBMITTED → IN_REVIEW ↔ NEEDS_INFO → ACCEPTED | DECLINED`

with requester `WITHDRAWN` paths before acceptance.

**ACCEPTED != appointment.**

### Flash

Founder-approved #12 states:

`AVAILABLE → HOLD_PENDING_PAYMENT → RESERVED → BOOKED`

Key semantics:

- hold = temporary exclusive claim, not confirmed;
- reserved = one confirmed customer, appointment not yet required;
- booked = confirmed reservation plus confirmed appointment;
- only one active exclusive customer may exist for a scarce Flash design;
- cancellation never silently re-releases Flash.

Exact hold/payment/refund semantics remain #14.

See `docs/product/tattoo-domain-semantics.md` for the full state and transition contract.

### Deposit

Proposed #14 definition for Founder review:

- Deposit = fixed monetary prepayment toward specific accepted Custom work or a specific Flash reservation;
- Deposit is credited toward the final tattoo price;
- artist may configure separate default Custom and Flash deposit amounts;
- Custom deposit may only be requested after ACCEPTED and does not create an appointment;
- Flash public reservation acquires an exclusive hold before payment;
- working V1 Flash hold duration = 15 minutes;
- successful Flash deposit during the active hold creates RESERVED;
- late payment after hold expiry can never override current Flash state;
- paid cancellation resolves explicitly to REFUNDED or RETAINED;
- cancellation never automatically re-releases Flash;
- artist owns the cancellation/refund policy;
- Tessnova must preserve artist-facing ownership of the client relationship.

Payment-provider and merchant architecture remain M4 decisions.

See `docs/product/tattoo-deposit-semantics.md` for the full contract.

### Artist Home
Issue #15 proposes a narrow morning screen showing public/Books state, actionable Custom Requests, active exclusive Flash holds, and the distinct Flash versus Deposit states. It does not invent calendar scheduling, CRM or automatic client messaging.

### Onboarding
Issue #15 proposes a structured shortest path: identity (name, city, styles), genuine permitted portfolio, explicit Books confirmation, a true client action, preview, then explicit publication. Flash and Custom Deposit configuration are conditional, not universal blockers.

**Publication is not automatically activation.** A truthful Books-CLOSED/no-Flash informational page may be public, but does not count as Issue #11 activation without a real Custom Request or eligible Flash path.

AI drafts are optional, fact-constrained, artist-reviewed, and never auto-published. Follow the [Issue #15 contract](tattoo-onboarding-ai-artist-home.md) for required/optional fields, conditional Flash deposit/policy gates, Artist Home state/actions, and M3 validation questions.

## Success metrics

Issue #11 defines the operational metrics in detail.

Current measures are:

1. **Time to usable bio link** — setup start until a live page the artist is willing to publish/use; working target median under 10 minutes.
2. **Qualified-request decision readiness** — percentage of submitted requests assessable without first asking for missing required qualification information; initial validation target >=80%.
3. **Qualification back-and-forth** — median clarification messages after a structured request; initial validation target <=1.
4. **Flash reservation integrity** — zero double-confirmed reservations for one scarce flash design; hard invariant.
5. **Commercial conversion** — at least one real external client completes a qualified request or flash reservation through Tessnova during validation.
6. **Retained workflow use** — repeated real workflow activity after activation; no hard percentage is approved yet because retention confidence remains medium-low.

See `docs/product/tattoo-v1-icp-jtbd-success.md` for definitions, evidence boundaries and M3 tests.

## Explicit postponements

- public slot picker
- full calendar
- CRM
- newsletter
- form builder
- custom-domain support as universal P0
- multi-artist studio workspace
- marketplace / public artist directory
- freeform theme editor
- carts
- proposal system
- contract generation
- referral program
- generic vertical framework
- generic rules engine
- speaker/event product code

## Visual requirement

The experience must not feel generic, dull or obviously AI-generated.

Issue #13 defines the proposed visual product contract:

- artist work remains visually dominant;
- themes vary composition, density, typography and image treatment—not merely colour;
- themes preserve Books / Flash / Custom Request semantics;
- mobile is the primary storefront context;
- theme customization stays curated rather than becoming a freeform builder.

Tesnova.com remains a craftsmanship / interaction-quality reference, not a source to copy. The detailed interaction/motion study remains M3 Issue #10.
