# Tattoo V1 — ICP, Jobs-to-be-Done and Success Metrics

**Status:** M2 definition for Founder approval  
**Issue:** #11  
**Scope:** Customer/outcome definition only. This document does not define Books/Flash/Custom Request state machines, storefront IA, deposit implementation, onboarding implementation, or technical architecture.

## 1. Evidence used

The primary evidence for this definition is TAT-01 and TAT-02, supported by the M1 evidence synthesis and ADR-004.

### Repeated evidence

Both Tattoo participants independently reported that:

- Instagram is a major discovery/acquisition channel;
- serious enquiries are mixed with friends, price-checkers and other social inbox noise;
- placement, size and references repeatedly have to be collected before the artist can assess a request;
- Books Open / Closed messaging does not reliably stop DMs;
- deposits are handled manually through PayPal;
- flash claim state is updated manually;
- flash double-booking has occurred;
- generic/shared-looking artist pages are undesirable.

Additional high-signal evidence:

- TAT-01 described a weak enquiry taking about five messages before discovering it was unsuitable.
- TAT-02 described a recent booking requiring roughly nine messages.
- TAT-02 lost a serious enquiry after it sat in Message Requests for 11 days.
- TAT-01 would replace the current bio link if clients could see work, minimum price and Books status, but not merely for a prettier Linktree.
- TAT-02 would switch if the experience looked better than Linktree and reduced low-quality price DMs.

These findings support the customer/problem definition below. They do **not** prove exact pricing, retention, onboarding speed, or payment-provider architecture.

## 2. Primary ICP

### Primary customer

Tessnova Tattoo V1 is for an **independent tattoo artist who owns the client relationship and receives meaningful inbound interest through Instagram/social/referrals, but still qualifies and manages that demand through fragmented manual tools**.

Typical fit signals:

- solo independent artist, chair renter, or artist working independently inside a shared studio;
- meaningful client discovery or enquiry volume from Instagram/social/referrals;
- custom enquiries currently handled in DMs, email or WhatsApp;
- repeated manual collection of placement, size, references and related qualification details;
- artist controls their own Books status, client communication and deposit policy;
- artist wants a distinctive professional presence rather than a generic profile/template;
- artist may offer scarce flash designs and manually manage claimed/reserved state.

### Strongest early-adopter signal

The strongest early-adopter profile is an independent artist who has **both**:

1. enough inbound social demand that qualification/inbox noise is a recurring burden; and
2. a stateful workflow problem such as flash reservation, Books status or deposits that a static bio-link cannot solve.

Flash is a particularly strong wedge because both interviewed Tattoo participants independently reported double-booking failures. Flash selling is therefore a high-value fit signal, **not** a mandatory condition for every V1 customer.

## 3. Explicitly excluded / not-primary customer types

Issue #11 does not define these groups as permanently unsupported. They are excluded from the **primary V1 ICP** so the first product remains narrow.

- **Multi-artist studio/shop operators buying for a team** — requires staff/workspace/permissions/operational concerns beyond the solo-artist problem.
- **Large studio chains or franchise-like operations** — materially different buyer, governance and workflow needs.
- **Artists primarily seeking a marketplace/directory for discovery** — Tessnova V1 is a direct professional presence and workflow product, not a demand marketplace.
- **Artists whose primary requirement is a public appointment-slot calendar** — public slot selection/full scheduling is explicitly outside Tattoo V1.
- **Businesses seeking CRM, newsletter, campaign or generic form-builder functionality** — these are not the product wedge.
- **Artists with little or no inbound demand yet whose main problem is audience creation** — Tessnova may improve presentation, but V1 is not primarily an audience-growth or social-discovery product.

The last exclusion is a current ICP boundary, not evidence that early-career artists can never benefit. M3 should test whether the product is still compelling for lower-volume artists without broadening V1 prematurely.

## 4. Top jobs-to-be-done

### JTBD 1 — Convert social discovery into credible next action

**When** a potential client discovers my work through Instagram/social/referral,  
**I want** one professional place that shows my work, context, Books status and the relevant way to proceed,  
**so that** serious clients can understand fit and take the right next action without first starting an ambiguous DM conversation.

### JTBD 2 — Qualify custom tattoo demand before manual conversation

**When** someone wants a custom tattoo,  
**I want** the essential assessment information collected before I spend time replying,  
**so that** I can quickly decide whether the request is suitable and reduce repetitive back-and-forth.

This job is about a **qualified request**, not an automatically booked appointment.

### JTBD 3 — Keep serious enquiries out of social inbox noise

**When** real client interest arrives,  
**I want** it to enter a dedicated Tattoo workflow instead of being mixed with social messages,  
**so that** valuable enquiries are less likely to be missed, buried or forgotten.

### JTBD 4 — Reserve scarce flash without double-confirming it

**When** a client wants a scarce flash design,  
**I want** the claim/reservation state to be unambiguous and exclusive,  
**so that** one design can never end up with two confirmed customers.

This is a hard product-integrity job, not merely a convenience feature.

### JTBD 5 — Tie commitment to the specific work being reserved

**When** money is required to secure a request or flash design,  
**I want** the deposit/reservation commitment associated with that specific work,  
**so that** the artist and client understand what the payment secures without Tessnova appearing to own the customer relationship.

Issue #14 will define the exact deposit semantics. Issue #11 defines only the customer outcome.

## 5. Activation definition

An artist is **activated** when they have a live Tessnova public URL that:

1. represents their work credibly enough that they are willing to use it as an Instagram/social bio link; and
2. exposes at least one real client-action path appropriate to their practice — Custom Request and/or Flash.

Activation is an outcome, not merely account creation or theme selection.

### Activation metric

**Time to usable bio link**  
Measure elapsed time from starting setup to the first live page the artist says they are willing to publish/use as their social bio link.

Working target for later product validation: **median under 10 minutes**.

The under-10-minute threshold is a product hypothesis, not M1 evidence. M3 should test it with a concrete onboarding/prototype flow.

## 6. Value and retention hypothesis

### Value hypothesis

The public storefront gets the artist out of ambiguous social DMs, but the **retained value** comes from the recurring workflow around qualified requests, Books status, scarce flash state and reservation/deposit commitments.

A prettier profile alone is insufficient. TAT-01 explicitly rejected switching merely for a prettier Linktree.

### Retention hypothesis

An activated artist will keep Tessnova in their client-acquisition flow when it repeatedly saves qualification effort or safely manages state that is currently manual.

Expected retention signals:

- the Tessnova link remains published/used after initial setup;
- real clients submit structured requests through it;
- the artist returns to review or act on new requests;
- Books status is updated when availability changes;
- artists who use Flash return to manage availability/holds/reservations;
- deposit/reservation state is used when relevant.

**Confidence: medium-low.** M1 selected the vertical but did not establish long-term retention. M3/prototype validation and later concierge/private beta must test this directly.

Do not use daily-active-user behavior as the default retention model. Tattoo demand can be episodic; useful recurring workflow activity is more meaningful than arbitrary daily engagement.

## 7. Success metrics and operational definitions

### 7.1 Time to usable bio link

**Definition:** elapsed time from setup start to a live page the artist is willing to publish/use in their social bio.

**Why it matters:** tests whether Tessnova can become a credible professional surface without a long builder workflow.

**Working target:** median **< 10 minutes** once onboarding is implemented.

**Current status:** hypothesis to validate in M3; not yet proven.

### 7.2 Qualified-request decision readiness

**Definition:** percentage of submitted Custom Requests that the artist can assess for basic suitability without first asking for missing required qualification information.

```text
decision-ready submitted requests
÷
all submitted custom requests
```

**Initial success target:** **>= 80%** decision-ready during prototype/concierge validation.

This target is intentionally outcome-based. Structural form completion alone is not enough if the artist still lacks the information needed to assess the request.

### 7.3 Qualification back-and-forth

**Definition:** median number of artist clarification messages required after a structured Custom Request before the artist can make a basic suitability/next-step decision.

**Initial success target:** median **<= 1** qualification clarification message.

M1 evidence shows current conversations can take about five to nine messages in observed examples. The target is a hypothesis to validate, not a claim derived from those two examples.

### 7.4 Flash reservation integrity

**Definition:** number of cases in which one scarce flash design has more than one confirmed customer/reservation.

**Hard success criterion:** **0**.

This is a product invariant. Any double-confirmed flash reservation is a correctness failure, regardless of aggregate conversion.

### 7.5 Real commercial conversion

**Definition:** a real external client, not the artist/tester, completes a qualified Custom Request or Flash reservation through Tessnova during concierge/prototype/beta validation.

**Minimum validation signal:** at least **one real commercial-intent conversion** through the product before claiming the loop is commercially validated.

When deposit functionality exists at the appropriate later stage, track whether the deposit is successfully tied to the corresponding request/design; Issue #14 defines those semantics.

### 7.6 Retained workflow use

**Definition:** after activation, the artist continues to use Tessnova for real workflow state rather than leaving it as a static abandoned page.

Evidence may include repeated real requests, Books changes, Flash state changes or reservation/deposit activity on separate occasions.

**No hard numeric retention threshold is approved in Issue #11.** M1 confidence on retention is medium-low; M3 and beta should establish a credible baseline before a retention percentage is treated as a gate.

## 8. M3 assumptions that must be tested

M3 should test these as hypotheses, not present them as established facts:

1. **Bio-link adoption:** target artists will actually put/keep the Tessnova URL in their Instagram/social bio.
2. **Visual credibility:** the storefront feels distinctive and professional enough to replace/add to current Linktree/manual-link behavior.
3. **Structured-flow adoption:** prospective clients will use Custom Request / Flash paths instead of defaulting to DMs often enough to create value.
4. **Qualification improvement:** artists can assess most structured requests with materially less clarification.
5. **Activation speed:** a credible publishable page can be configured in under ~10 minutes without a blank-page-builder experience.
6. **Flash wedge strength:** artists who sell scarce flash see reservation integrity as materially valuable, not merely convenient.
7. **Retention mechanism:** operational workflow, rather than static presentation, is strong enough to keep Tessnova in ongoing use.
8. **Lower-volume fit:** artists with less inbound demand may benefit, but should not cause V1 to drift into an audience-growth product.
9. **Price/value fit:** around EUR 19/month remains plausible only if the demonstrated workflow value is strong; exact pricing is not closed by Issue #11.

## 9. What Issue #11 does not decide

The following remain for later M2 issues:

- exact Books states/semantics — #12;
- exact Flash state machine — #12;
- Custom Request schema/states — #12;
- storefront information architecture/themes — #13;
- deposit/hold/refund/cancellation semantics — #14;
- onboarding implementation, AI assistance and Artist Home — #15;
- Events reuse/stress-test — #16;
- final P0/P1/postponed V1 scope and M2 closure — #17.

It also does not select framework, database, auth, payment provider or deployment architecture.

## 10. Issue #11 closure test

Issue #11 is complete when the Founder approves this definition such that M3 can evaluate:

- **who** the Tattoo V1 prototype is for;
- **which jobs** it must solve;
- **what activation means**;
- **what retained value is hypothesized to be**;
- **how success/failure will be measured**;
- **which assumptions remain unproven**.

Founder approval of Issue #11 advances M2 to Issue #12. It does **not** authorize production implementation.
