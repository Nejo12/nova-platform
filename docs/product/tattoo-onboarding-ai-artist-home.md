# Tattoo V1 — Onboarding, AI Assistance and Artist Home

**Status:** M2 Issue #15 product definition — proposed for Founder approval  
**Issue:** #15  
**Scope:** Onboarding inputs and sequence; draft/publication/activation semantics; bounded artist-facing AI drafting; Tattoo Artist Home information architecture and actions. This is a product contract for M3 low-fidelity design, **not** a production implementation specification or M2 closure.

## 1. Authority, evidence and decision labels

### Approved product inputs (not reopened here)

- **ICP, outcomes and activation:** [Issue #11](tattoo-v1-icp-jtbd-success.md). Activation requires a **live, credible artist bio link with an actual Custom Request and/or Flash client-action path**; working median setup target is under 10 minutes. The time target is unvalidated.
- **Books, Flash, Custom Request:** [Issue #12](tattoo-domain-semantics.md) and [Tattoo glossary](tattoo-domain-glossary.md). Books OPEN/CLOSED concerns new Custom Request intake; Flash inventory is independent. Custom Request ACCEPTED is not an appointment.
- **Storefront composition:** [Issue #13](tattoo-storefront-ia-themes.md). One mobile-first page; identity/Books, visible work, conditional Flash, context, process/policies, next action; curated compositionally distinct themes.
- **Money and scarce inventory:** [Issue #14](tattoo-deposit-semantics.md). Separate fixed artist defaults for Custom and Flash deposits; Flash requires a positive configured deposit for the public claim path; 15-minute exclusive hold; payment during an active owned hold leads to RESERVED; payment and appointment state are distinct. Artist owns refund/cancellation policy.
- **M2 Figma:** [canonical approved M2 frame](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=8-2). It specifies social → public work/Books/Flash → Custom Request or Flash Hold → Deposit/Reservation → Artist Home; no production code before M2 closure.

### Direct research evidence

- [TAT-01](../validation/interviews/TAT-01.md) and [TAT-02](../validation/interviews/TAT-02.md): Instagram-led discovery, repeated placement/size/reference questions, important Books visibility, manual PayPal deposits, Flash double-booking, and rejection of generic-looking artist pages.
- [M1 synthesis](../validation/evidence-synthesis.md): strong repeated Tattoo workflow pain, but **no direct evidence** for a particular onboarding step order, a preferred default Books state, an AI-assistance conversion lift, a portfolio photo count, or the optimal Artist Home layout.
- [Assumptions register](assumptions.md): structured onboarding and under-10-minute activation are hypotheses, not measured outcomes.

**Classification throughout:** “Approved” refers to already merged #11–#14 contracts. “Proposed #15” marks product behavior for the Founder to approve through this PR. “M3 test” means a prototype hypothesis, not a fact or engineering requirement. No AI usefulness claim is presented as interview evidence.

## 2. Proposed #15 product outcomes and constraints

The minimum valuable setup is **not** a fully filled website. It is a credible artist-led page with truthful Books state and a useful next step, configured without a blank editor. The artist may publish without Flash or AI. Onboarding must not demand deposit/provider onboarding, an appointment calendar, a custom domain, or long-form website copy.

- **Trust first:** show real tattoo work, identity, city and style. Do not generate or fake portfolio pieces.
- **Truthful states:** an artist must explicitly confirm whether new Custom Requests are accepted; no implied calendar availability.
- **Progressive disclosure:** ask only what is relevant to the selected Custom/Flash path; allow later enhancement.
- **Publication safety:** media intended for public display requires affirmative confirmation that the artist is authorized to publish it. A separate M2 closure decision owns the complete media-publication-permission rule; this issue does not invent legal consent machinery.
- **Fast path:** the setup path for a Custom-only artist should not be blocked by Flash, paid deposits, AI generation, detailed policies, or a theme editor.
- **No implementation leap:** no auth, schema, payment processor, notification transport, storage, or localization architecture is chosen here.

## 3. Onboarding: shortest structured sequence (proposed #15)

| Stage | Artist input/action | Why now? | May defer? |
| --- | --- | --- | --- |
| 0. Begin private draft | Account exists; a private/unpublished draft is available. | No empty public page or silent publication. | No public effect until publish. |
| 1. Establish identity | Artist/business **display name**, **city**, **one or more primary tattoo styles**. Studio name/context only when applicable. | First public decision zone must establish who/where/style. | Required core fields cannot be deferred past publish. |
| 2. Show work | Add **at least one** authentic representative portfolio image; affirm publication authority for each public item. | Work is credibility, not decoration. | Extra images, captions and curation may wait; zero portfolio images cannot publish. |
| 3. Set Books | Explicitly confirm **OPEN** or **CLOSED**; review the resulting Custom Request availability. | Avoid accidentally inviting intake. | Must confirm before publish. |
| 4. Choose public path | If Books OPEN, enable the approved structured Custom Request path. Optionally add Flash; if Books CLOSED, offer Flash where ready or truthful supporting navigation. | Preserve an accurate client next step. | Flash is optional; never force it into the Custom-only path. |
| 5. Check essentials | Confirm visible preview, public images, action text and any policy applicable to an enabled payment path; choose the default curated theme or another curated option. | Prevent misleading publishing. | Bio, FAQs, SEO and cosmetic customization may wait. |
| 6. Publish | Artist **explicitly** publishes the verified preview and receives a shareable link; Artist Home displays link and real workflow state. | Account creation or draft preview must never publish automatically. | Publishing is a deliberate action. |

### Defaults and minimal field rules

- **Books:** treat draft as **CLOSED by default for safety**, but require explicit artist confirmation of OPEN/CLOSED before first publish. This is a proposed setup default, **not a third Books domain state**, and no automatic opening is implied. M3 must test whether an explicit no-preselection choice is clearer.
- **Theme:** offer one editorially credible curated theme as the starting presentation; allow a bounded alternate selection without requiring theme configuration. The number and actual visuals are M3 decisions.
- **Portfolio minimum:** propose one representative real tattoo-work image as the hard input minimum; do not claim one image alone always meets an artist's credibility threshold. The artist reviews the preview and decides whether it represents their work credibly. M3 tests whether more examples are needed in practice.
- **Studio information:** optional where the artist does not have a stable named studio; city and working context must still be truthful. Do not fabricate an address or public studio name.
- **Price floor:** optional. A price list, quote engine and auto-pricing are not prerequisites.
- **Bio and process text:** a short deterministic explanation of the approved request flow can appear without AI; any personal biography or specific commitment must be supplied/approved by the artist. Long bio/FAQ/SEO text is optional.
- **Custom Deposit default:** optional during first publication. Only becomes necessary before an artist actually presents a Custom Deposit as DUE **after ACCEPTED**. Do not solicit deposits during initial Custom Request submission.
- **Flash Deposit default:** required, **positive**, fixed and currency-labelled **before enabling a public Flash claim path**. No invented amount or currency default. An artist may set this after initial publication, when adding Flash.
- **Artist-owned policy:** request/process instructions should be truthful. A cancellation/refund policy intelligible to the client is required **before the respective deposit payment**, not necessarily before a Custom-only no-deposit page is published. No universal 48-hour or other refund rule.
- **Flash selection:** default is **no published Flash**. Existing Flash material may remain an unpublished draft until required imagery, publication authority, payment amount, artist policy and availability state are confirmed. Uploading Flash never reserves it.
- **Reopening note, Guest Spot, social links, studio detail, extra images:** optional. Reopening notes do not automatically reopen Books or create a waitlist.
- **Locale/currency:** do not assume a German-only or multilingual launch. The separate M2 initial-locale decision remains open; any public deposit amount must display a specific currency.

### Two concrete fast paths

**A. Custom-only independent artist:** identity + style + city → permitted portfolio image(s) → explicitly select Books OPEN → review the real Custom Request entry point and preview → publish. Skip Flash setup, deposit amount, AI, long bio and theme tweaking. The request still collects all #12 mandatory client qualification fields when a client submits.

**B. Flash-first artist with Books CLOSED:** identity + style + city → permitted portfolio → confirm Books CLOSED → enter published Flash design(s), available state, positive fixed Flash deposit with currency, clear artist cancellation/refund policy and authorized image(s) → verify hold/reservation explanation → publish. Books CLOSED must not block Available Flash.

## 4. Publication readiness is not activation (proposed #15)

Use the following **product milestones**, not implementation enums:

    Account created
       ↓
    Private storefront draft exists
       ↓ completeness and honest-action checks
    Ready to publish
       ↓ explicit artist action
    Public storefront live
       ↓ credible to artist AND working Custom Request/Flash action
    Activated (Issue #11 outcome)

| Milestone | Product meaning | Not sufficient on its own |
| --- | --- | --- |
| Account created | Artist has begun the relationship with Tessnova. | No public identity/work/action. |
| Draft exists | Private preview may be incomplete, with no publicly callable request/reservation. | Unpublished is not activation. |
| Ready to publish | Required identity, work, Books state, permitted media, accurate next action and relevant financial policy gates are satisfied. | Readiness is not a published URL. |
| Public/live | Artist explicitly made the page public; visible states and action links are truthful. | A live informational page is not necessarily #11 activation. |
| Activated | Artist says the live link credibly represents their work **and** a real Custom Request or eligible Flash reservation path is actionable. | Account, view count, social link or template selection alone. |

### Readiness rules

1. **Identity:** display name, city, tattoo style(s), and truthful relevant studio context.
2. **Real work:** at least one representative public portfolio image, with the publication-authority confirmation specified above.
3. **Explicit Books:** artist confirms either OPEN or CLOSED. CLOSED disables **new** Custom Request submission; existing requests continue.
4. **Truthful next step:** provide an enabled Custom Request path if OPEN, or a valid Flash claim path for AVAILABLE Flash, or (for a CLOSED/no-Flash informational page) an honest **supporting social/contact navigation** that does **not** claim to accept new requests. Never invent a waitlist or bookable dates. An informational page may publish but does **not** count as activated under #11.
5. **Client clarity:** Custom Request is described as a qualification request; Flash hold is described as temporary; no “booked” claims without actual appointment confirmation.
6. **Conditional payment:** do not expose public Flash reservation until exclusive inventory state, positive fixed amount/currency and artist cancellation/refund policy are ready. Custom Deposit can remain unset until an ACCEPTED request triggers a later optional deposit.
7. **Permission:** no public display of media without artist publication-authority acknowledgement; exact record/wording/legal approach awaits the standalone M2 media-permission decision.

**Important distinction:** allowing a Books-CLOSED/no-Flash artist to publish an *informational* profile protects the approved Books semantics and research observation of artists currently CLOSED. It must never inflate the activation metric, and supporting contact links must remain secondary. M3 should test whether this “published but not activated” state is understandable and valuable.

### Readiness/activation examples

| Scenario | Can publish? | Counts as #11 activation? | Explanation |
| --- | --- | --- | --- |
| Books OPEN, authentic portfolio, qualified Custom Request enabled, no Flash/deposit default | Yes | Yes, after artist credibility confirmation | Fastest functional Custom-only path. |
| Books CLOSED, valid AVAILABLE Flash, configured Flash deposit and policy | Yes | Yes, after artist credibility confirmation | Flash action is independent of Books. |
| Books CLOSED, no Flash, truthful supporting social/contact action | Yes — informational | **No** | Visible portfolio/Books, but no qualifying Tessnova Custom/Flash conversion path. |
| Books CLOSED, no Flash, no visitor next step | Not yet | No | Offer a truthful supporting navigation option or reopen an actual action path. |
| Books OPEN, no public portfolio image | Not yet | No | Credibility/public-content gate missing. |
| Books OPEN, Flash draft without valid deposit/policy | Yes, **without publishing the Flash** | Yes via Custom Request | Unready optional Flash must not block Custom-only activation. |
| Books CLOSED, Flash draft with no amount or no authorized image | Only as informational page with supporting action | No | An unsafe Flash claim must never go public. |
| Flash is RESERVED/BOOKED only; Books CLOSED | Informational publish possible | No | Claimed Flash is not a new actionable reservation path. |
| Previously activated page later switches Books CLOSED, with no Available Flash | Remains live and truthful | Do not rewrite historical first-activation event | Current available conversion path can drop to none; track current actionability separately from historical activation. |

## 5. Dependencies and exceptional onboarding cases

- **Book-status changes:** setting Books CLOSED after publication stops only *new* Custom Request submission; existing SUBMITTED/IN_REVIEW/NEEDS_INFO requests remain accessible in Artist Home and may continue.
- **Flash is optional:** no empty Flash component in public IA or an unused Flash “setup required” task blocking publish. Flash can be added after activation through a bounded item-creation flow.
- **Unready Flash item:** retain as private draft until artist provides authorized design media, one-scarce-design availability meaning, deposit amount/currency and relevant policy. No visible public AVAILABLE-claim promise before readiness.
- **Portfolio permission withdrawn:** affected image must cease public display until permission is valid again; if this leaves no publishable portfolio, the artist sees a clear readiness problem. Precise legal handling/permission verification belongs to the separate M2 decision and architecture later.
- **Artist starts CLOSED:** no silent conversion to OPEN to satisfy the activation KPI; informational publishing is allowed with honest navigation but does not become measured activation.
- **Artist cannot finish:** keep draft private and resumable; never show placeholder claims, fabricated work or missing policies as public facts.
- **Theme switching:** never changes Books, Flash, Custom Request, Deposit or permission semantics.
- **Payment limitations:** the approved product contract is specified here, but no provider integration is assumed available during M2. M3 prototypes must represent the intended states honestly; M4 must make live payments/reservations safe before a transactional launch.
- **Media distinction:** artist public portfolio/Flash assets and private client-uploaded Custom Request references are not interchangeable. Client request reference images never become public portfolio media by default.

## 6. Optional, bounded AI assistance (proposed #15)

AI is a **drafting helper**, never the source of artist facts, legal policy, medical authority, workflow decisions or publication authority. The core storefront can be completed fully without AI.

| Supported drafting task | Artist-provided source | AI may produce | Human review rule |
| --- | --- | --- | --- |
| Short artist bio | Artist-supplied name, style, factual background and desired voice | Readable alternative phrasing | Artist verifies each biographical/credential claim. |
| Request / booking instructions | Approved #12 request meaning, artist-confirmed process, Books state | Clear explanation of how to request work | No appointment promise or auto-opening Books. |
| FAQ draft | Artist's actual answered questions, prices/policies **only if supplied** | FAQ phrasing and organization | Artist confirms every answer; no invented amount, dates or rules. |
| Tattoo preparation notes | Artist-authored general process notes | Plain-language formatting | No diagnosis, medical claim, procedural medical instruction or unsupported universal advice. |
| SEO title/description | Artist-confirmed identity, location, style and work | Concise search-friendly copy | No invented credentials, ranking, reviews, locations or service availability. |

**Workflow:** artist chooses a supported task → supplies/chooses known factual source → requests draft → edits or rejects → explicitly approves final text → text may be included in a later explicit publish/update action. AI generation **never** alters live public text automatically and cannot publish on behalf of the artist.

**Non-negotiable exclusions:**

- Do not invent prices, deposit amounts or final quotes; all money uses artist-defined values and the #14 Deposit contract.
- Do not invent cancellation/refund terms, date promises, Books availability, appointments, portfolio facts, credentials, reviews, biography details or medical claims.
- Do not select a Books state, release/reserve Flash, accept/decline Custom Requests, request deposits, send client messages, or decide refunds on its own.
- No prompt-to-website, AI site builder, generic form/workflow generation, autonomous marketing, or freeform layout engine.
- Do not supply private client messages or Custom Request reference images as AI drafting input by default. Consent/provider/data-retention decisions, if ever necessary, belong to later privacy/architecture work.
- Do not assume that an AI model or provider has been approved.

**Fallback:** if AI is disabled, unavailable, too slow or produces invalid text, preserve the artist's existing inputs and edits; offer ordinary manual copy entry and a small **deterministic** description of the supported Custom Request flow. Failed drafting must not block saving, publishing or accessing Artist Home.

**Validation status:** usefulness of AI assistance, trust and saved onboarding time are **M3 hypotheses**. AI is not a measured participant requirement; do not make it an implicit P0 dependency. Final P0/P1 assignment belongs to #17.

## 7. Artist Home: information architecture (proposed #15)

Artist Home answers: **What is currently open for new client action, and what needs my attention?** It is not a general CRM, appointment system or business analytics dashboard.

### Morning-screen hierarchy

1. **Status/header:** public/draft status, live link/share action, prominent **Books OPEN/CLOSED control**, and simple “preview/edit storefront” access. Explain that Books only governs new Custom Requests.
2. **Needs attention:** active exceptions first (notably late Flash payment that cannot reserve a design), then **new SUBMITTED requests**, requests in **IN_REVIEW**, and artist-owned next steps tied to accepted work/deposit decisions. A list item opens its specific Tattoo record.
3. **Flash and deposits:** active **HOLD_PENDING_PAYMENT** design count/expiry, then RESERVED/BOOKED Flash and deposit DUE/PAID/REFUNDED/RETAINED where relevant. Do not merge the Flash inventory state with its money state.
4. **Contextual empty/status messaging:** “No new Custom Requests”, “Books Closed — new requests paused”, “No Flash published” or “No active holds”, as appropriate. No generic business widgets.

Do not require the artist to check Artist Home daily. Tattoo work is episodic; the retained-value measure is meaningful repeat workflow activity, not DAU.

### Tattoo-state/action matrix

| State/event | Artist Home display | Artist action/priority | Boundary |
| --- | --- | --- | --- |
| Draft / not published | Readiness checklist and preview; share URL not yet live | Complete essentials; explicitly publish | No false public availability. |
| Live + Books OPEN | “Accepting new Custom Requests” status | May explicitly close Books | Never means an appointment slot is open. |
| Live + Books CLOSED | “Not accepting new Custom Requests” status | May explicitly reopen Books | Existing requests remain accessible; Flash independent. |
| Custom Request SUBMITTED | New request, key qualification summary and timestamp | Review / begin assessment | Not an appointment. |
| Custom Request IN_REVIEW | In-progress request and provided information | Accept, decline or request clarification | No deposit can be requested until ACCEPTED. |
| Custom Request NEEDS_INFO | “Waiting for client details” with outstanding clarification | Review after client responds; do not mislabel as a fresh booking | Return to IN_REVIEW after information arrives. |
| Custom Request ACCEPTED | Accepted qualified request | Optional Custom Deposit request; continue artist-controlled arrangements | No automatic appointment/date, quote or deposit. |
| Custom Request DECLINED/WITHDRAWN | History/detail, not an action queue item | No further qualification action required | Do not silently reopen. |
| Flash AVAILABLE | Published claimable design | Optionally manage design/publication | Only AVAILABLE can acquire a client hold. |
| Flash HOLD_PENDING_PAYMENT | One active exclusive claim and remaining hold time (15-minute working rule) | Usually informational; no competing confirmation action | Hold is **not** RESERVED; one owner only. |
| Flash hold expires unpaid | Hold disappears from active list; design becomes AVAILABLE | No manual release required for an expired unpaid hold | A late payment must not steal later ownership. |
| Flash RESERVED | One confirmed customer; deposit PAID for the active hold | Arrange/record appointment through a separately approved future boundary | **Not** BOOKED without confirmed appointment. |
| Flash BOOKED | Reservation with confirmed appointment | Manage within approved scope | Not claimable; never relist automatically. |
| Custom Deposit DUE | Due only on an ACCEPTED Custom Request | Follow up through artist-owned workflow; show amount/currency | Do not mark the request “booked”. |
| Custom Deposit PAID | Paid against the specific ACCEPTED request | Preserve financial record and next-step clarity | Payment alone is not appointment confirmation. |
| Flash Deposit PAID | Show alongside the particular design reservation | Confirm reservation only if paid during that client's active hold | Do not assume any successful transfer grants inventory. |
| Late Flash payment after hold expiry | Explicit **exception/needs resolution** linked to deposit and design | Resolve without automatically confirming/reselling design | Financial exception is **not** a new approved Deposit status or Flash status. |
| Paid cancellation | Deposit disposition becomes REFUNDED or RETAINED | Artist resolves outcome under own policy | No automatic Flash release; artist explicitly releases when appropriate. |
| No new requests / no active holds | Accurate empty state and optional action to preview/share storefront | No manufactured urgency | Avoid “0 revenue”/generic KPI cards. |

**Actions remain deliberate:** opening/closing Books, publishing Flash, assessing a request, presenting a Custom Deposit, recording a financial outcome and releasing Flash require proper artist-authorized actions at the later implementation stage. This document does not invent notification services, automatic client messaging or an appointment calendar.

### Home scenarios that M3 must storyboard

1. **Books Closed + Available Flash:** clearly show intake paused **and** a separately claimable Flash design.
2. **Books switch while reviewing requests:** previously submitted requests remain reviewable; no silent decline or waitlist.
3. **Two clients want one Flash:** one active 15-minute hold; the second cannot acquire a concurrent hold, pay for a reservation, or be marked confirmed.
4. **Hold expires while payment is delayed:** item returns to AVAILABLE if unpaid at expiry; a subsequently confirmed late payment becomes an exception and never overrides another customer's state.
5. **Accepted Custom Request + PAID deposit:** remain separate from appointment confirmation; artist sees the associated deposit and request, not a falsely “booked” job.
6. **Cancellation of RESERVED Flash:** resolve deposit REFUNDED/RETAINED and require explicit artist release before the item can become AVAILABLE.
7. **Newly activated Custom-only artist:** no Flash empty panel demanding setup; clear Books and new-request information.
8. **Published informational page, Books Closed and no Flash:** no new-request CTA; Home gives a truthful status and does not claim activation.

## 8. Mobile-first and accessibility product constraints

- Onboarding should be completable on a phone, with a clear step purpose, visible progress, saved private draft and minimal unnecessary typing; no desktop-only upload or theme canvas requirement.
- Portfolio selection/preview must reveal enough detail for a credible tattoo judgement. Public media must not appear before permission confirmation.
- The publication gate should explain the exact missing requirement with a route to correct it; optional enhancements must never look mandatory.
- Artist Home's first screen prioritizes Books truth and genuine work requiring attention, not vanity statistics or navigation depth.
- Flash timer, hold owner/expiry meaning, money amount/currency and unavailable/reserved states must be readable without hover, colour alone, or animation.
- Keyboard operation, focus management and assistive labels are required for later interactive designs; reduced-motion alternatives apply if M3 introduces motion.
- Curated theme and generated-copy presentation must preserve status clarity across long names, empty Flash collections, variable media crops and narrow viewports.
- Exact visual layouts, accessible component choices, breakpoints, performance budgets and implementation tests belong to M3/M4.

## 9. M3 prototype tests and decision questions

**Test with independent artists and realistic public visitors, separating artist self-report from actual task outcomes.** Proposed scenario measures:

| Prototype question | Observable measure | Status |
| --- | --- | --- |
| Can a Custom-only artist reach a credible live shareable link in under 10 minutes? | Elapsed setup-to-usable-link time, median; observe skips/errors | Working #11 target, **unvalidated**. |
| Is one real representative work image sufficient for a credible initial page? | Artist would/would-not use as bio link; audience ability to assess style | New #15 hypothesis. |
| Is default CLOSED + explicit confirmation safer/clearer than no default? | Accidental OPEN publication; selection comprehension | New #15 hypothesis. |
| Do artists distinguish informational publication from activation? | Can identify when real Custom/Flash client action exists | New #15 hypothesis. |
| Can Books CLOSED coexist with independently AVAILABLE Flash without confusion? | Correctly locate valid Flash claim; do not attempt Custom Request | Tests #12/#13 contract. |
| Does gated Flash configuration avoid unsafe claim paths without delaying Custom-only artists? | Invalid payment/policy item never exposed; setup delay | New #15 hypothesis. |
| Does the Home action hierarchy surface missed requests and late-payment exceptions quickly? | Time to find/triage relevant record; mistaken “booked” assumptions | New #15 hypothesis. |
| Do artists understand HOLD_PENDING_PAYMENT → RESERVED → BOOKED? | Accurate state explanations; zero double-confirmed scenario outcome | Approved #12/#14 invariant; M3 UX test. |
| Does AI materially reduce copy-writing time without misinformation? | Review/edit effort, detected fabricated facts, skip rate | Unproven AI value hypothesis. |
| Do clients find required request fields decision-ready without heavy clarification? | >=80% decision-ready; <=1 median clarification message in later validation | Working #11 targets, not current measured results. |

Use prototype findings to revise proposed thresholds, default choices, visual copy and priority **through explicit Founder review**. Do not reinterpret M1 evidence as proof of the hypotheses above.

## 10. Exclusions and deferred decisions

**Out of #15 and V1 unless separately approved:** generic site or AI website generator; freeform theme/page builder; public slot calendar; auto-booking; CRM; newsletters; customer segmentation; generic task management/analytics; multi-artist workspace; artist marketplace; generic booking/rules/vertical engine; appointment date guarantees; automatic customer messaging; unreviewed AI publication.

**Separate M2 inputs before #17:** standalone media-publication permission product rule; initial language/locale decision (including any necessary supported currency implications). This #15 document states conditional readiness, not legal mechanisms or a locale selection.

**M3:** actual onboarding and dashboard screen designs; theme compositions/count; optional copy controls; state/timer treatment; motion; usability tests including Books-default, credibility and publication/activation distinction; Issue #10 design-reference study.

**M4:** auth/session architecture; data schema; state persistence; concurrency and idempotency; payment provider/merchant model, payout/refunds/chargebacks; media storage and rights-record implementation; routing/public URL implementation; AI model/provider and security/data-retention contract; notifications; technical accessibility checks.

**#17 only:** final P0/P1/postponed classification and explicit **Founder M2 closure**. Approval of this #15 definition does not close M2, begin M3 automatically, or authorize production implementation.

## 11. Founder approval checklist — Issue #15 only

Merging the bounded #15 PR would approve **the proposed product definitions here**, including:

- [ ] Structured fast-path onboarding rather than a blank editor; no mandatory Flash or AI.
- [ ] Required first-publication inputs (identity, city, style, real permitted portfolio, explicit Books) and conditional money/policy requirements.
- [ ] Safe draft Books CLOSED default **with explicit publish-time confirmation**, subject to M3 comparison with no preselection.
- [ ] Minimum one authentic public portfolio image as a readiness **floor**, with credibility tested separately.
- [ ] Flash only publicly claimable after required amount/currency/policy/media/inventory checks; Custom Deposit may be configured later.
- [ ] Explicit draft → ready → live → #11 activation distinction; Books-CLOSED/no-Flash informational publication never counted as activation.
- [ ] Optional factual AI drafting with artist review and explicit publication; manual fallback.
- [ ] Artist Home Books/request/hold/deposit priority and the state/action matrix without invented CRM/calendar semantics.
- [ ] M3 assumptions and separate media-permission/locale decisions remain visible; no M4 choices are authorized.

If any of those material proposals is unacceptable, **do not merge**; adjust this #15 contract first. The Founder performs the merge manually.
