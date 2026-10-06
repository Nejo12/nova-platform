# M3 — Tattoo V1 User Flows, Batch 1

**Status:** DRAFT — Founder design review required; not a tested or approved interaction prototype  
**Tracking:** [M3 Issue #35](https://github.com/Nejo12/nova-platform/issues/35)  
**Canonical editable Figma artifact:** [M3 — Tattoo V1 User Flows · DRAFT #35, flow frame](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=22-3)  
**Figma page:** `22:2` · **root frame:** `22:3`  
**Inputs:** [Founder-approved Tattoo V1 P0/P1 scope](../product/tattoo-v1-approved-scope.md), [Books/Flash/Custom Request contract](../product/tattoo-domain-semantics.md), [Deposit contract](../product/tattoo-deposit-semantics.md), [onboarding and Artist Home](../product/tattoo-onboarding-ai-artist-home.md), [media permission](../product/tattoo-public-media-permission.md), [German-first language rule](../product/tattoo-initial-language-locale.md), [M3 interaction-quality study](references/tesnova-com.md), and [NOT_NOW.md](../../NOT_NOW.md).

## 1. Batch outcome and evidence

Created an **editable native Figma flow board** on a separate **new M3 draft page** in the existing canonical file. It comprises **four user-flow lanes, 34 explicit steps and decision/exception annotations**. Existing approved M2 material and other Figma pages were preserved.

**Independently inspected:** Figma plugin confirmed the page and root frame exist, the flow frame is **1650 × 1513**, four lanes are present, and a screenshot was inspected. Initial auto-layout incorrectly constrained the horizontal lanes to 80px height; that defect was fixed before review. Screenshot now shows all four lanes and their exception cards legible with no apparent clipping or overlap.

**Not yet verified:** participant comprehension, prototype links, actual payment behavior, mobile responsive layouts, complete German user-facing screen copy, screen-reader experience or reference-site runtime motion. This is a **flow-map artifact**, not production screens, executable code, prototype-testing evidence or Founder design approval.

### Figma lanes

| Lane | Flow intent | M2 authority / key boundary |
| --- | --- | --- |
| 01 — Artist | Private draft → name/city/styles → public portfolio authority → explicit Books → conditional action path → preview/publish → live link → Artist Home | #15 publication is deliberate; publishing ≠ activation; #28 per-asset public permission |
| 02 — Client Request | Discover artist → Books gating → tattoo-specific qualification and private references → SUBMITTED → IN_REVIEW ↔ NEEDS_INFO → ACCEPTED/DECLINED or pre-acceptance WITHDRAWN → optional post-acceptance Deposit | #12 Request is a lead, never an appointment; closing Books doesn't lose existing requests |
| 03 — Client Flash | Browse AVAILABLE Flash → single exclusive 15-min HOLD_PENDING_PAYMENT before paying → artist-owned fixed credited Deposit → RESERVED only on valid payment → separately BOOKED after appointment; expiry, retries, late payments, cancellation/release | #12/#14 one scarce design can never have two confirmed customers |
| 04 — Artist Home | Status/Books → triage requests → monitor holds → resolve deposit exceptions → maintain artist-owned client relationship → withdraw disputed images → restore readiness → accessible outcomes | #15/#28 operational focus rather than CRM or generalized booking |

The overview is **sequential** for readable low-fidelity communication, but branches are represented with explicit status conditions and exceptions inside gate cards. **Do not misread a vertical visual arrow as a universal mandatory transition.** Conditional routes need explicit separate screen maps/prototype connections in subsequent M3 work.

## 2. Approved M2 product behavior, translated into flow decisions

### A. Publishability and activation

- Begin unpublished. Require display name, city, primary tattoo styles, and at least one **authentic, authorized** public image.
- The artist explicitly chooses Books **OPEN** or **CLOSED** before publication. A working draft default of CLOSED is an M3 **hypothesis**, not a third domain state.
- If OPEN, show an actually usable Tattoo Custom Request path. If CLOSED, no new Custom Request, but independent AVAILABLE Flash remains possible.
- A Flash item is only publicly claimable when media authority, AVAILABLE state, a positive fixed credited Flash Deposit amount with actual currency and understandable artist-approved German cancellation/refund policy are present.
- Artist inspects preview and deliberately publishes. An honest informational page with CLOSED/no claimable Flash may be public but **not count as activated**. The artist must judge the link credible **and** a Custom/Flash action must be working before activation.
- Withdrawn image permission blocks public usage without silently changing Books, Flash financial disposition or the original activation record.

### B. Custom Request and client privacy

Required: placement, approximate size in centimetres, black/colour, one or more references, short idea, cover-up yes/no, approximate requested month/window, reply contact. **Budget optional.**

- SUBMITTED does **not** reserve a date or claim a tattoo.
- IN_REVIEW ↔ NEEDS_INFO captures request clarification; ACCEPTED or DECLINED ends qualification.
- WITHDRAWN is available **before** acceptance via approved transitions.
- ACCEPTED ≠ appointment, final quote or Deposit paid. Custom Deposit is an **optional later step, only after ACCEPTED**.
- Client reference images (especially cover-ups) remain private. Never repurpose as public portfolio assets by default.
- Books switching CLOSED stops **new** submissions, without invalidating requests already submitted.

### C. Flash, Deposit and cancellation

- Every scarce Flash design grants **at most one active exclusive hold and one confirmed customer**. Books does not control Flash.
- The working 15-minute hold begins **before payment**. Retry is only legitimate within the same active hold.
- Deposit is **positive, fixed, artist-configured, currency-labelled and credited** toward specific tattoo work. No invented percentage, currency, fees or refund window.
- Successful payment by the **same active holder within expiry** grants RESERVED; BOOKED requires separately confirmed appointment/date.
- Unpaid expiry returns AVAILABLE. Payment confirmed too late **never reclaims or double-reserves** a design, even if another customer currently holds/reserved it. The exception requires explicit resolution.
- Refund or retain is an explicit financial outcome; a confirmed Flash design returns to AVAILABLE only after proper disposition **and an independent artist release**.
- Withdrawing public imagery blocks new public claims relying on that image but must not automatically refund, release or corrupt existing payment/reservation state.

### D. German UI and accessibility

- Approved initial system UI is **German**, for both artist and client. Genuine user-authored text may remain in English or other languages.
- Design must distinguish Books OPEN/CLOSED, temporary HOLD, RESERVED, BOOKED and Custom Request ACCEPTED with text, not color/motion alone.
- A payment screen must expose correct amount/currency, credit toward final price, artist ownership and understandable cancellation/refund terms **before payment**.
- Keyboard/focus, touch, reduced motion, legible error and expiry messages need interactive M3 validation. A hold countdown should not announce every second to screen readers.
- Public author imagery and private client references require distinct preview and access treatment.

## 3. Next screen/prototype mapping — after flow review

This batch **does not contain responsive screen UI**. After Founder agrees on the conceptual branches, prioritize a **bounded second M3 design task**:

1. **Artist fastest path:** onboarding identity, authorized work upload, explicit Books selection, conditional Custom path, preview and publish confirmation, Artist Home first-use.
2. **Mobile client path:** public artist identity/work/Books, Custom Request required fields, upload privacy, submit confirmation and no-appointment explanation.
3. **Flash edge-state screens:** AVAILABLE, single-holder pending payment, payment attempt and time remaining, RESERVED without date, BOOKED with date, expiry, second client blocked, late payment exception.
4. **Artist exception screens:** requests needing info, payment disposition/release, permission withdrawal, lost-last-image readiness.
5. **German copy and accessibility pass:** realistic artist/client labels, reduced-motion/focus controls, touch target and state comprehension.

The final visual design must have editorial craft and distinct curated themes, but may **not** copy Tesnova.com's external code, layout, palette, images or identity. Its live interaction behavior remains unverified under Issue #10, which stays open until browser inspection is completed or the Founder explicitly narrows that issue.

## 4. Draft review scenarios / acceptance matrix

| Scenario to put in front of artist/client | Expected correct comprehension | Status |
| --- | --- | --- |
| OPEN Custom-only artist publishes without Flash, deposit or optional AI | Credible public page with real request action; no extra payment blocker | **Not tested** |
| CLOSED artist has independently AVAILABLE Flash | Custom Request unavailable; eligible Flash still claimable | **Not tested** |
| CLOSED with no Flash, supporting navigation | Informational public page, not activation | **Not tested** |
| Client submits complete request | Qualification only, not immediate appointment | **Not tested** |
| Client uploads cover-up reference | Private to request, never public portfolio | **Not tested** |
| Artist accepts request | No appointment until separately arranged; Custom Deposit optional after acceptance | **Not tested** |
| Two people try to claim one Flash | One active hold only; other client blocked until valid expiry/release | **Not tested** |
| Client pays during hold | RESERVED, not BOOKED | **Not tested** |
| Client's hold expires then payment arrives late | Never second confirmed customer; explicit exception | **Not tested** |
| Artist cancels reserved work | Resolve REFUNDED or RETAINED then artist explicitly re-releases, if chosen | **Not tested** |
| Portfolio permission is withdrawn | Public image hidden; no silent Flash re-release; readiness flagged | **Not tested** |
| English artist biography + German system flow | No misleading bilingual-language support claim | **Not tested** |
| Reduced motion / keyboard / small touch target | All content and critical actions still available | **Not tested** |

### M3 success measurement

Use #11's already-approved metrics: median under **10 minutes** to artist-credible live link (hypothesis), qualified request decision readiness **≥80%** (target), median clarification messages **≤1** (target), Flash double-confirmation **zero** (hard invariant), actual first external conversion and real retained activity without an invented retention threshold.

## 5. Founder decision and phase boundaries

**Requested design review:**

- Are the four lanes and their branch/exception boundaries a faithful expression of Tattoo V1?
- Is the shortest artist Custom-only publication path correctly separated from optional paid Flash?
- Are the difference between Custom acceptance, Flash reservation and an actual booked appointment clear?
- Which specific edge-state screens should come before visual theme explorations?
- Approve **only this low-fidelity conceptual direction**, or request changes; later canonical responsive screen designs and user testing remain separate M3 gates.

**Issue #35 remains OPEN until explicit Founder review approval.** Producing this draft does not silently close it.

**Not authorized here:** production source code, framework/database/provider/transaction choices, Events/Speaker app code, multi-artist CRM, generic calendar/vertical engines, new public media consent machinery, Figma visual-theme signoff or M4 start. Founder performs all repository merges manually.
