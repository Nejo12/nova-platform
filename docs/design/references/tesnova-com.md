# Design Reference — Tesnova.com · M3 Interaction-Quality Study

**Reference:** https://www.tesnova.com/  
**Status:** M3 research and original Tessnova design-direction proposal; **live interaction matrix recorded 2026-10-10** in Cursor cloud Chrome and Playwright Chrome. GitHub [Issue #10](https://github.com/Nejo12/nova-platform/issues/10) is already **Founder-closed**; this file no longer claims verification is pending. M3 phase closure and M4 remain Founder-gated.  
**Source of truth:** This document is the repository reference study for [Issue #10](https://github.com/Nejo12/nova-platform/issues/10).  
**Originally recorded:** 2026-10-06  
**Study date:** 2026-10-06; live browser addendum 2026-10-10  
**Purpose:** Carry the Founder's quality benchmark into Tattoo V1 design **without copying** the external site's code, visual identity, content, photography, compositions or layouts.

## 1. Evidence provenance and confidence

**A. Founder-identified aspects of the reference (qualitative preference, not independently observed runtime behavior)**

The original [Issue #10](https://github.com/Nejo12/nova-platform/issues/10) and this file identify a strong desired impression of intentional movement and craft, especially:

- pointer/cursor responses;
- hover states and component micro-interactions;
- entrance/scroll effects and section transitions;
- color/background rhythm, typographic hierarchy and depth;
- responsive polish and careful animation timing.

These observations record **what the Founder wants to study**, not an instrumented measurement of the reference website.

**B. Directly retrieved content hierarchy (verified from publicly accessible page text)**

A web-indexed text/html retrieval of https://www.tesnova.com/ (the index reports a crawl roughly two months before this study) exposes:

- a named hero with two prominent actions (portfolio and project contact);
- sections for work/services, UI/development and recent projects;
- a pricing guide with distinct package selections and CTAs;
- a team/company story, testimonial sections and a contact form;
- navigation, footer and additional services links.

This supports a **reported progressive information hierarchy and repeated contextual actions**, but not an observed visual rhythm, not a conclusion about exact animation curves, colors, cursor code, page-load speed or interaction quality. The domain is a software-development agency, not a tattoo product; its agency portfolio, pricing and contact sections **must not be transplanted into Tessnova**.

**C. Browser verification attempt (incomplete; no fabricated results)**

A desktop Chromium/Playwright attempt to navigate the external site returned **`net::ERR_BLOCKED_BY_ADMINISTRATOR`**. Consequently the following remain **UNVERIFIED** in this environment: cursor/pointer implementation, hover animation and exit behavior, actual scroll triggers, animation duration and easing, responsiveness at 375/768/1440px, keyboard/focus order, reduced-motion behavior, accessibility quality, CLS, frame timing, media weight and network performance.

Do **not** describe the 2026-10-06 blocked attempt as observed interaction quality. A later browser-enabled session is recorded in §10. A screenshot of a static marketing asset is **not** equivalent to a measured interaction. This section remains the historical blocked-attempt record.

**D. Accessibility authorities for proposed Tessnova requirements (not endorsements of the reference)**

- [W3C WCAG 2.2 — Animation from Interactions (SC 2.3.3)](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html): disable nonessential interaction-triggered motion; `prefers-reduced-motion` is a suitable mechanism. The SC is **AAA**, so do not inaccurately call it a WCAG AA requirement.
- [W3C WCAG 2.2 — Pause, Stop, Hide (SC 2.2.2)](https://www.w3.org/WAI/WCAG22/Understanding/pause-stop-hide.html): the Level **A** requirements apply to qualifying moving/auto-updating material.
- [W3C WCAG 2.2 — Focus Visible (SC 2.4.7)](https://www.w3.org/WAI/WCAG22/Understanding/focus-visible.html) and [Content on Hover or Focus (SC 1.4.13)](https://www.w3.org/WAI/WCAG22/Understanding/content-on-hover-or-focus.html): pointer-only state and obscured focus are not acceptable for interactive task flows.
- [W3C WCAG 2.2 — Target Size Minimum (SC 2.5.8)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html): touch interaction constraints should be assessed as part of visual craft; don't replace a real accessible control with a decorative hotspot.

## 2. Translation boundary — what we may learn, not copy

| External reference / desired impression | Original Tessnova design principle | Evidence category | Not allowed |
| --- | --- | --- | --- |
| Purposeful animated hierarchy | **Meaningful sequence**: immediately visible artist, real work, Books and next action; motion may support scanning but never delay access | Page content structure verified; timing unverified | Copying hero layout, section geometry, text or illustration |
| Pointer/hover playfulness | **Affordance before flourish**: subtle spatial/color feedback on controls, with visible equivalent for keyboard focus and touch | Founder interest; live effect unverified | Custom global cursor replacing native pointer, cursor trails or exclusive hover-only content |
| Rich work/project presentation | **Artwork as evidence**: real permissioned Tattoo work, edge-to-edge where useful, accurate scale and no image filtering that hides detail | External has work sections; Tattoo emphasis from approved #13/#17 | Reusing external portfolio assets, mock images or software-agency service cards |
| Distinctive section composition | **Curated contrast**: changes in density, type scale, rhythm, image placement and deliberate background transitions per theme | Founder quality preference, Tattoo #13 theme contract | Recreating external palettes, exact layouts or brand signatures |
| Responsive transitions | **Continuity across context**: focus, state, scroll position and input values preserved through meaningful transitions | Hypothesis; externally unverified | Route changes that trap focus, delay actionable content or introduce mandatory preloader |
| Depth / dimensionality | **Editorial layers**: foreground tattoo detail and restrained surface separation | Proposed for M3 validation | Universal parallax, heavy 3D transforms or behind-the-pointer effects |
| Repeated relevant calls to action | **Truthful state-driven CTA**: Books OPEN requests, Books CLOSED supporting navigation and separately AVAILABLE Flash | External CTAs verified; Tattoo rules approved | Imported agency “book a call” funnels or false instant-appointment promises |
| Premium interaction polish | **Reliability is craft**: accessible forms, stable reserved/held states, predictable feedback and performance under weak connections | Tattoo #12/#14 and WCAG standards | Visual polish that hides Flash scarcity or Deposit conditions |

**Brand principle:** borrow an interaction-quality threshold, **not the identity**. The reference's software services, package pricing, imagery, brand wording, icons, palette and page layout are excluded as product/content templates.

## 3. Original proposed Tessnova motion language — M3 design hypothesis

**Working name:** *Editorial Precision*. This is a descriptive design hypothesis, **not** a finished brand system or a committed implementation.

**Design laws**

1. **Clarity first:** the content and next action must be legible and actionable with animation disabled, media slow to load, keyboard-only input or touch.
2. **Tattoo work is the hero:** choreography must not pull attention away from real work or make clients overlook authorized portfolio detail.
3. **State changes are explicit:** Flash AVAILABLE → HOLD_PENDING_PAYMENT → RESERVED and eventual BOOKED require textual state changes. Motion is supplementary, never the sole semantic carrier.
4. **One purposeful gesture per interaction:** no simultaneous cursor trail, image tilt, marquee and section reveal fighting for attention.
5. **Speed reflects risk:** playful treatment may appear on gallery hover; money, permission withdrawal, timeout and error handling use restrained, immediately comprehensible feedback.
6. **Every motion pattern has a reduced-motion and keyboard/touch counterpart.**

**Candidate timing tokens for prototyping (not measured from Tesnova.com, not implementation requirements yet)**

| Pattern | Proposed duration | Proposed behavior and guardrail |
| --- | --- | --- |
| Focus/hover color, underline, small emphasis | ~100–180 ms | Direct feedback; avoid moving interactive targets away from fingers/cursor |
| Button press or lightweight panel expand | ~120–220 ms | Clear target feedback; keep focus/order stable |
| Small disclosure/overlay opening | ~180–260 ms | Animate only if it does not delay screen-reader/keyboard availability |
| Editorial media/section entrance | ~240–420 ms | Once, restrained distance/opacity; no essential content concealed before observer trigger |
| Context transition, where useful | ~180–320 ms | Preserve request input and Flash state; never block route navigation or async status |
| Active Flash countdown | **Elapsed 15-minute actual product rule** | Show readable time/expiry text without aggressive pulsing or decorative tick animation |

**Candidate easings:** outward deceleration for entry (e.g. a modest ease-out curve), inward acceleration for exit, and immediate/direct feedback for errors and confirmations. Exact cubic-bezier, spacing, theme values and durations must be chosen through M3 prototypes—not reverse-engineered from the reference.

**Perceptual budget:** a decorative transition should not delay a primary CTA becoming actionable. Any continuous animation must have a clear functional purpose and must be paused or eliminated where the accessibility criteria apply. Avoid geometry-driven scroll jumps and large layout shifts. Quantitative animation/performance budgets are **M3/M4 validation tasks**, not benchmark numbers from the reference.

## 4. Pattern decision table — accept / constrain / reject

| Pattern | Current M3 decision | Placement and rationale |
| --- | --- | --- |
| Underline/color/outline response on hover **and focus** | **Adopt principle** | Both product UI and public storefront; state cues remain visible on touch |
| Short intentional page/section entrance | **Explore cautiously** | Public storefront editorial content only; media/CTA never hidden when motion disabled |
| Artwork crossfade/transition within curated themes | **Explore cautiously** | Portfolio with approved assets, preserving detail and media-permission restrictions |
| Small, purposeful state-change feedback | **Adopt principle** | Books, Custom Request feedback, Flash/Deposit; textual outcome mandatory |
| Controlled spacing and tonal shifts between sections | **Explore cautiously** | Tattoo storefront themes; distinct compositions without generic site editor |
| Strong visible keyboard focus and touch targets | **Mandatory design constraint** | Product and public; not a decorative optional effect |
| Loading/hold state with accessible text | **Mandatory design constraint** | Flash/Deposit and media updates, including no-motion presentation |
| Custom global pointer replacement/trail | **Reject by default** | Pointer constraints, reduced accessibility and distraction relative to Tattoo work |
| Heavy continuous parallax / scrolling depth effect | **Reject by default** | Motion sensitivity, battery/performance and focus/scroll issues |
| Scroll hijacking/snap that controls user navigation | **Reject** | Conflicts with keyboard, browsing history, touch and request data entry |
| Autoplay infinite marquees or moving testimonial strips | **Reject by default** | Distracts from real artist content; must comply with Pause/Stop/Hide if used at all |
| Motion-only notification or availability status | **Reject** | Money and scarcity state cannot rely on color, movement or a fleeting toast; **one scarce Flash design must never have two confirmed customers** |
| 3D tilting/perspective over private client uploads | **Reject** | Privacy/credibility hazard; no connection to qualification task |
| Complex shared animation/runtime package | **Not authorized** | No generic vertical or animation engine without independently proven reuse |

This is a product-specific **M3 recommendation**. None of these choices approves code, theme assets, Figma edits or new shared Nova UI behavior.

## 5. Product UI versus Tattoo public storefront

| Surface | Recommended intensity | Allowed examples | Hard exclusions |
| --- | --- | --- | --- |
| **Public artist storefront** | Modest editorial expressiveness | Curated portfolio scale transitions, quiet reveal of supporting text, responsive section rhythm | No generic site layout, stock work, claimable RESERVED Flash, hidden Books state |
| **Books control** | Minimal | Immediate text/visual confirmation OPEN/CLOSED | No animation that implies future bookable slots or changes state on scroll |
| **Custom Request** | Task-first | Clear field help, validation/focus response and explicit status outcomes | No carousel/transition that loses references or required input |
| **Flash AVAILABLE claim** | Restrained urgent clarity | Distinct, legible AVAILABLE, active 15-minute hold and explicit expiry | No fake scarcity effects, animation that adds a second customer, payment-triggered appointment claim |
| **Deposit / refund** | Near-static high trust | Confirm work/amount/currency, status and policy text with accessible feedback | No delayed success, celebratory motion that obscures money, forced countdown flashing |
| **Media permission** | Near-static high trust | Explicit unchecked per-asset acknowledgement; easy withdrawal warning | No aesthetic effect that reveals private images or consent claims |
| **Artist Home** | Quiet operational | Focus/hover, state transitions, loading/error/empty messages | No animated CRM dashboard, marketing metrics or theme-builder preview |
| **Onboarding/preview** | Focused editorial | Progress/completion indication; optional gentle preview transitions | No animation as a prerequisite to publish or material hidden behind AI effects |

**Ownership boundary:** Nova UI remains responsible for generic accessible primitives and tokens. Tessnova owns Tattoo-specific presentation composition, domain-state interaction and curated theme variants. Do **not** publish tattoo semantics into Nova UI because a motion primitive happens to be shareable.

## 6. Accessibility and reduced-motion acceptance scenarios

**Must be designed and tested for each pattern in M3:**

- **`prefers-reduced-motion: reduce`:** nonessential transforms, parallax, scroll reveals and large movement disappear; essential state text, hover/focus indication, loading/Flash expiry and request errors remain. A change to reduced-motion preference should not trap focus or hide content.
- **Keyboard and focus:** Tab/Shift+Tab reveals correct visible controls; Escape dismisses eligible overlays, focus returns sensibly; tooltips/reveals cannot demand hover only. Never animate focus off the visible viewport or reorder focus unexpectedly.
- **Touch/mobile:** actions accessible without hover, without custom cursor affordances, with sufficient target size/spacing and no gesture-only path.
- **Screen readers:** provide semantic labels and live/response messaging where warranted, not animation-only availability; a 15-minute hold duration should not produce an announcement every second.
- **Media:** no unauthorised client photograph/preview in page, OG card, public thumbnail or transition frame. If rights are withdrawn, the visual is removed without silently mutating Flash reservation.
- **Contrast:** text/button/status remain legible throughout transitions and across curated background changes. Semantic statuses cannot depend on hue alone.
- **Flash/money:** keyboard users can distinguish AVAILABLE, temporary exclusive HOLD, confirmed RESERVED and appointment BOOKED; late payment is not represented as successful claim.
- **Slow/offline media:** main CTA and booking/status truth do not depend on large hero imagery loading. A missing image is handled honestly, not replaced with fabricated artwork.
- **Pause controls:** any qualifying automatic animation follows the appropriate WCAG 2.2.2 requirement. Essential progress feedback can remain static.
- **User testing:** test real German client/artist wording and comprehension; English authored portfolio does not create an unsupported English system UI.

## 7. Required live-reference browser verification — RECORDED 2026-10-10

The matrix below was the required observational checklist. Results from the 2026-10-10 Cursor/Playwright session are in §10. Capture timestamp, viewport and evidence; label the site itself as the **external reference**. Do not treat GitHub issue closure as a substitute for this record.

| Scenario | Minimum evidence to capture | Pass/fail question |
| --- | --- | --- |
| Desktop pointer/hover at 1440×900 | Short screen recording or sequential screenshots; note interactive targets | What actually changes on hover? Does it recover on fast mouseout? |
| Page scroll/entrance | Scroll through hero, work, projects and contact; record behavior | Which movements are actual vs imagined? Are contents accessible without triggering? |
| Navigation/section transitions | Test internal nav, back, focus and a section CTA | Are transitions stable, interruptible and non-blocking? |
| Keyboard-only | Tab/Shift+Tab across visible links/buttons and Escape | Do reference controls show focus and preserve order? **Record observed result without treating it as Tessnova acceptance.** |
| Mobile touch 375×812 and tablet 768×1024 | Capture screenshots and tap relevant controls | Which patterns survive mobile without hover? Is content readable? |
| Reduced motion | Enable OS/browser emulation then repeat entrance/hover/scroll | Does actual reference respond? Record facts, not assumptions. |
| Performance | Review media requests, long animations, load/layout shifts in DevTools | Which ideas would be expensive on a mid-range device? Do not invent timings or Lighthouse scores. |
| Cross-check Figma | Compare resulting *principles* against approved Tattoo #13/#17 and canonical Figma | Does any proposed interaction distort Books/Flash/Request/Deposit semantics? |

**Verification owner/routing:** Founder or Claude Code Agent on Mac using a real browser, or a browser-enabled Work session, **only for read-only observation**. Do not upload/download/copy external proprietary source assets. Capture notes/video of behavior for internal evidence with reference attribution and avoid reusing external visuals in product design.

**Closure criterion:** GitHub Issue #10 was Founder-closed on 2026-10-07 while this document still required a runtime matrix. The 2026-10-10 session records that matrix with limitations. A documentation PR still does **not** approve M3 closure or M4. If the Founder wants an additional Mac-native pass, that is a new explicit request, not an implied reopen.

## 8. Founder review and M3 follow-on

- [ ] Confirm the desirable qualities: responsive feedback, visual rhythm, distinct editorial themes, truthful CTA, deliberate microinteractions.
- [ ] Reject global cursor trails, parallax-heavy pages, scroll hijack and automatic visual distraction by default.
- [ ] Confirm storefront-versus-product separation and no import of agency site content/identity.
- [ ] Approve *testing* the candidate motion range—not hard-coded production tokens.
- [ ] Confirm accessibility/reduced-motion, privacy and paid Flash semantics are gating design constraints.
- [x] Live reference interaction verification recorded on 2026-10-10 (see §10); remaining gaps are labeled as limitations, not as successful tests.
- [x] GitHub #10 is already Founder-closed; this document no longer instructs agents to keep it open. Do not auto-reopen or declare M3 approved.

**M3 deliverables after this reference:** user-flow and low-fidelity Tattoo prototype work in the canonical Tessnova Figma; independent artist/client research; visual theme exploration; approved interaction-spec and accessible states. No M4/production implementation is authorized.

---

*Research stance: preserve Founder intent; separate directly retrieved site structure, independently verified standards, unobserved behaviors, and original Tessnova design hypotheses.*


## 9. Live browser verification — 2026-10-07

**Outcome: BLOCKED — reference homepage fails with a client-side exception in this cloud browser.** This is a new browser attempt, not completion of §7. Keep Issue #10 **OPEN**.

### 9.1 Environment and methodology

- Live repository precheck: `main = 69219a01a0a9dd1c0677264b0d588bc012755a8d`, matching the task's starting SHA.
- Read `AGENTS.md`, Issue #10 and its comments, this reference, roadmap, approved Tattoo V1 scope and `NOT_NOW.md`. No open PR was returned by the precheck.
- Issue #37 is closed/completed. Its [Founder approval record](https://github.com/Nejo12/nova-platform/issues/37#issuecomment-6038145624) explicitly approves the design direction without asserting browser/accessibility/legal/usability verification. The [#10 gate record](https://github.com/Nejo12/nova-platform/issues/10#issuecomment-6038147242) identifies this as the remaining active M3 reference task. M4 remains unauthorized.
- Attempt: **2026-10-07, 12:53–12:55 UTC / 14:53–14:55 Europe/Berlin**. Site-origin console error timestamps were `12:53:54.047Z` on initial opening and `12:54:05.103Z` after the single reload.
- Browser: remote cloud **Chrome**, CDP connection; exact browser version and remote operating system **not verified**. This is not the Founder's local Mac browser.
- Initial viewport was the browser default, **not verified as 1440 × 900 CSS pixels**. A viewport screenshot was inspected, but image dimensions are not treated as a verified CSS viewport or device profile. The requested desktop/mobile/tablet emulations were not completed.
- Reduced-motion preference: **not verified or changed**. A read-only environment-metadata query failed because this browser interface did not expose `navigator`; it supplied no usable metadata. Do not confuse that inspection failure with the site's separately captured exception.
- Target: fresh homepage at https://www.tesnova.com/, followed by **one reload**. Read the accessibility tree, inspected a screenshot and read the browser console log. No forms were submitted, source downloaded, assets reused or site code modified.

**Observed browser result:** both the initial load and reload exposed only an application-error heading instead of the usable homepage. The inspected screenshot likewise showed a white page with the client-side exception message.

**Observed console result:** a site-origin `TypeError: Cannot read properties of null (reading 'getExtension')` was recorded on both attempts, attributed to a site-served layout script. A separate browser-extension metadata error also appeared; it is not attributed to Tesnova.com. No source code was fetched to diagnose either error.

This is **not** the earlier `ERR_BLOCKED_BY_ADMINISTRATOR` outcome, and no evidence identifies it as a bot challenge. It does not establish that the site is broken for all visitors. Root cause, graphics support and behavior in another browser remain unknown.

### 9.2 Desktop pointer / hover observations

**Blocked, not tested:** no usable hero, header, CTA, link, project card or image target was exposed. Default/hover entry/hover exit, geometry, target displacement, feedback type, perceived duration and rapid mouse-in/out recovery cannot be reported. No reference cursor treatment was verified.

### 9.3 Scroll / entrance observations

**Blocked, not tested:** hero, services, UI/development, projects, pricing, testimonials/company and footer could not be traversed. First/repeated reveals, stagger, pinning, parallax, background rhythm, section overlap, rapid scrolling and layout stability remain unverified. Error-page stillness is not evidence that the reference has no motion.

### 9.4 Navigation / transition observations

**Blocked, not tested:** homepage navigation and CTAs were unavailable. Back/Forward restoration, rapid navigation, transition interruption, preloaders and focus transfer were not exercised as reference-site interactions. Reloading the error page is not a successful navigation audit.

### 9.5 Keyboard / focus observations

**Blocked, not tested:** the error heading is not the reference's intended control set. Tab/Shift+Tab, Enter, Space, Escape, focus visibility/order, hover-only information, overlay focus trapping and restoration remain unverified. No WCAG conformance conclusion follows.

### 9.6 Mobile — 375 × 812

**Not run:** no verified mobile emulation or touch pass. Menu, hero, projects, CTAs/forms, sticky elements, scaling, overflow, clipping, crowding and narrow-screen motion remain unverified. The default-browser error is not a mobile result.

### 9.7 Tablet — 768 × 1024

**Not run:** no verified tablet emulation. Intermediate composition, portrait navigation, grids, spacing, typography and hover assumptions remain unverified.

### 9.8 Reduced-motion result

**Not run:** `prefers-reduced-motion: reduce` was not enabled and verified. There is no evidence about what changes, stops or persists under that preference, nor about availability of essential content in that mode. Do not claim that the reference ignores reduced motion.

### 9.9 Performance implications

**Observed:** the attempted homepage did not remain usable in this browser and produced the same site-origin exception after reload.

**Unverified:** media weight, repeated requests, scroll handlers, animation CPU cost, idle motion, layout-shift metrics, FPS, load timings and mobile performance. No Network/Performance trace or Lighthouse run was captured; cache state was not controlled, so neither attempt is a cold/warm benchmark.

**Inference:** a runtime failure can prevent evaluation of the intended interaction layer. This evidence does not identify a specific animation technology or prove an expensive effect caused the failure.

**Tessnova recommendation:** decorative enhancement should fail without removing core artwork context, truthful status, navigation or transaction explanations. This is a design resilience requirement, not a selection of M4 architecture.

### 9.10 Observed fact versus inference

| Category | Statement | Evidence / limit |
| --- | --- | --- |
| Observed fact | The homepage displayed a client-side application-error heading on opening and after one reload. | Live accessibility snapshots; screenshot inspected after reload. Limited to this cloud browser. |
| Observed fact | Both attempts logged a site-origin null `getExtension` TypeError. | Timestamped console entries; no source inspection or root-cause diagnosis. |
| Observed fact | #37 is completed with explicit Founder design approval; #10 remains open; M4 is not approved. | Live GitHub issue/comment records and roadmap at the stated base. |
| Inference | The runtime error prevents assessment of intended reference interactions in this session. | The intended homepage was unavailable; not a claim about every browser. |
| Unverified hypothesis | A particular graphics capability or decorative effect might explain the error. | **Not established.** Do not turn the error text into an implementation finding. |
| Tessnova recommendation | Essential content and state meaning must survive failure of decorative enhancement. | Original product-specific resilience principle; not a behavior observed on the reference. |

### 9.11 Recommendation changes and Tattoo product cross-check

Preserve §§2–6 as **original proposed Tessnova principles**, not runtime findings. No hover, timing, responsiveness or motion hypothesis has been validated or disproved by this failed load. Add the resilience recommendation above; do not change candidate timings or approve an implementation.

| Approved Tattoo rule | Consequence for proposed motion / failure handling |
| --- | --- |
| Books is request-intake status, never a public slot calendar. | OPEN/CLOSED and its explanation remain immediately legible without decorative effects. |
| Custom Request is qualification; ACCEPTED is not an appointment. | Success feedback must state the actual request outcome and preserve entered/private data. |
| Flash is scarce; one design cannot have two confirmed customers. | Animation cannot grant a claim, imply inventory, or override authoritative state. |
| HOLD is temporary and exclusive before payment. | Hold/expiry text remains explicit; animation completion never establishes ownership. |
| RESERVED follows a valid reservation; BOOKED requires independent appointment confirmation. | Distinct text survives transitions; no reservation celebration implies an appointment. |
| Deposit meaning, actual amount/currency and policy precede payment. | No reveal, loading flourish or failure fallback conceals money/policy meaning. |
| Private references stay private; public media requires permission. | No transition frame/fallback exposes private media; public removal does not release Flash or change payment state. |

Ownership stays unchanged: Nova UI generic accessible primitives/tokens; Tessnova Tattoo state behavior and storefront composition. Storefront-only editorial exploration remains restrained; operational, money and permission surfaces stay task-first. Existing rejections of cursor replacement, heavy parallax, scroll hijacking and motion-only status remain **Tessnova recommendations**, not claims that Tesnova.com uses those patterns.

**Historical correction:** §1.C remains accurate as the record of the earlier attempt. This attempt reached a different failure state. It does not establish that the site's design changed since the indexed retrieval or previous research.

### 9.12 Final Issue #10 closure assessment

**BLOCKED — material live interaction evidence remains unavailable. Do not close #10.**

Existing worthwhile-principle, rejection, original motion-language, accessibility/reduced-motion and ownership recommendations are documented. The required live desktop, scroll, navigation, keyboard, mobile, tablet, reduced-motion and performance observations are still missing. A documentation merge cannot substitute for them or authorize M4.

**Continuation:** run the existing §7 matrix and the requested interaction checklist in a browser where the reference renders successfully, recording browser/version/OS, exact CSS viewport, reduced-motion state, timestamps and behavior evidence. The Founder or Claude Code Agent on the Founder's Mac is the existing repository-approved route for that independent session. If the site also fails there, record that environment-specific result rather than inventing observations. No need to repeat completed repository documentation work.

This update references #10 without automatic closure. Founder review/merge remains manual; Figma, production code and phase gates are unchanged.

§9 remains the 2026-10-07 blocked-session record. GitHub later closed #10 on that merge. §10 is the later successful homepage observation and does not rewrite the blocked-session facts.


## 10. Live browser verification — 2026-10-10

**Outcome: HOMEPAGE RENDERED — §7 observational matrix recorded with labeled limitations.** This is a new browser attempt after the 2026-10-07 client-side exception. It is **not** M3 approval, **not** a WCAG/performance certification of Tesnova.com, and **not** permission to copy the site.

### 10.1 Environment and methodology

- Live repository precheck: `main = 54431144a95925ae5df8a182a8566126664b4271` (merge of PR #41).
- Read `AGENTS.md`, Issue #1, Issue #10 (state **CLOSED**, Founder-closed 2026-10-07T13:03:12Z), Issue #10 comment requiring the runtime matrix, Issue #37 (CLOSED, Founder design-direction approval), this reference, and `docs/roadmap/roadmap.md`.
- **Discrepancy observed before this session:** GitHub #10 closed; this file and Issue #1 still described #10 as open and verification as pending/blocked. No issue was auto-reopened.
- Attempt window: **2026-10-10, approximately 20:24–20:29 UTC / 22:24–22:29 Europe/Berlin**.
- Browsers (read-only observation):
  1. Cursor cloud Chromium/Electron. `navigator.userAgent` reported `Cursor/3.22.12 Chrome/148.0.7778.280 Electron/42.10.0` on a Macintosh UA string. This is not the Founder's local Mac browser.
  2. Playwright Chromium. `navigator.userAgent` reported `Chrome/155.0.0.0` on a Macintosh UA string.
- Exact remote OS patch level: **not independently verified** beyond those UA strings.
- No forms submitted. Chat widget suggested-replies were not used. No source downloaded for reuse. No Tesnova assets copied into the repository.

Verified CSS viewports via `window.innerWidth` / `innerHeight` (not screenshot pixel dimensions):

| Intended profile | Playwright measured | Cursor cloud measured |
| --- | --- | --- |
| Desktop 1440×900 | 1440×900 (`devicePixelRatio` 1) | 1440×900 (`devicePixelRatio` 1) after `Emulation.setDeviceMetricsOverride` |
| Mobile 375×812 | 375×812 | 375×812 (`devicePixelRatio` 2) |
| Tablet 768×1024 | 768×1024 | **Not reliably held.** After the tablet override, Cursor reported 1188×1584. Tablet layout numbers below are Playwright-only. |

Default `prefers-reduced-motion`: **no-preference** (`matchMedia` false) until explicitly emulated.

### 10.2 Desktop pointer / hover — 1440×900

**Observed:**

- `html` and `body` computed `cursor` was `auto`. Interactive links/buttons used native `pointer`. No custom cursor graphic, cursor-trail node, or pointer-replacement overlay was found in the inspected cursor-related class/id sample.
- Hero “See our work”: default color `rgb(255, 150, 33)` on a transparent background; 1px solid orange border; `transform: none`; size 166.48×50 CSS px. While hovered, color became `rgb(255, 255, 255)`; size and transform unchanged. After leaving the control, color returned to `rgb(255, 150, 33)` at the same size.
- First project card while hovered: `box-shadow` present (`0 20px 25px -5px` / `0 8px 10px -6px` at 10% black); `transform: none`; transition duration `0.3s`. Card image `transform` remained `none`.
- `matchMedia('(hover: hover)')` was true in Playwright.

**Limitations:** no screen recording; hover recovery was sampled once, not as a high-frequency mouse-in/out stress. Perceived duration was not measured with a timer. This is not a claim about every control on the site.

### 10.3 Scroll / entrance — 1440×900

**Observed:**

- Document `scrollHeight` was about 12822–13062 CSS px at desktop. `window.scrollTo` reached the requested Y values (0, 900, 2500, 6500, max, back to 0). Scroll position was not hijacked to a different value in this sample.
- 33 elements matched `scroll-fade` / `scroll-slide` class names. Count of those with a `visible` class: 8 at Y=0 and Y=900 and Y=2500; 16 at Y=6500; 26 at the bottom; 28 after returning to top (reveals did not all re-hide).
- Named running CSS animations at default motion included `neon-gradient-move` (~4000 ms, linear), `pulse-glow` (~2000 ms), and `float` (~6000 ms), plus some `CSSTransition` entries. Those named animations remained running while scrolling.
- Hero heading, supporting copy and the two primary CTAs were present in the accessibility tree without requiring a scroll trigger.
- Testimonials region included cards whose bounding boxes extended far past the viewport width (sample right edges beyond 3900 CSS px), consistent with a horizontal overflowing testimonial row rather than a fully wrapped grid.

**Limitations:** easing curves and exact entrance distances were not measured. Pinning/parallax were not isolated with DevTools layers. Rapid-fling scroll was not tested.

### 10.4 Navigation / transitions

**Observed:**

- `GET https://www.tesnova.com/showcase` loaded `https://www.tesnova.com/showcase` with title starting `Showcase | Tesnova Solutions`.
- Playwright `page.goBack()` returned to `https://www.tesnova.com/` with the original homepage title.
- Opening the bubble menu (`Toggle menu`, `aria-pressed="true"`) showed a full-viewport overlay (`.bubble-menu-items`, `aria-hidden="false"`) listing Home / Projects / Estimation / Pitch Project / Book A Call and further items.
- One `Escape` keypress while that overlay was open did **not** close it (`aria-pressed` remained `"true"`, overlay `display: flex`). A subsequent click on the toggle was intercepted by the overlay (`subtree intercepts pointer events`). A programmatic `click()` on the toggle also left the overlay open in that sample.
- Header computed style included `transition-all` with duration `1500ms`. Interruptibility of that transition was not separately timed.

**Limitations:** in-page hash/section-link smoothness was not separately measured. Showcase internal project pages were not opened. Overlay close via a visible overlay item was not completed because the overlay intercepted the toggle and Escape failed in this sample.

### 10.5 Keyboard / focus

**Observed native Tab order (Playwright, desktop, first 13 focused nodes after load):**

1. Logo link `/` — outline `rgb(0, 95, 204) auto 1px`, in view.
2. “Free Consultation” `/book-a-call` — outline style `none`.
3. Left-rail home `/` — native blue auto outline, in view.
4–7. Facebook, Instagram, TikTok, LinkedIn — orange auto outlines, in view.
8. “Toggle menu” — native blue auto outline.
9. “Toggle theme” — `rgb(23, 23, 23) auto 3px`.
10. Email `mailto:` — native blue auto outline.
11. “See our work” — outline style `none`.
12. “Book a 20-min call” — outline style `none`.
13. “Contact Us→” — outline style `none`, **not in view** at that moment.

Shift+Tab from item 13 returned to “Book a 20-min call”. Escape on that focused CTA did not move focus (no overlay was open in that later sample).

**Limitations:** this is not a complete focus-order audit of the whole page, skip-link check, screen-reader pass, or WCAG conformance result. Several primary CTAs had `outline-style: none` while focused; whether a non-outline focus treatment remained visible was not visually confirmed beyond computed style.

### 10.6 Mobile — 375×812

**Observed (Playwright numbers):**

- `innerWidth` 375, `innerHeight` 812. “See our work” geometry: x=8, width=359, height=50 (full-width stacked treatment versus the 166 CSS px desktop width).
- `documentElement.scrollWidth` 417 versus 375 (`overflow-x: hidden` on the root). Horizontal overflow existed in the layout measurement even if clipped.
- Toggle-menu control remained in the tree. Hero copy and both primary CTAs remained in the accessibility tree.
- Touch-specific gesture paths were **not** exercised (no tap-hold, swipe, or pinch). Hover-only behavior was not re-tested at this width.

**Cursor cloud:** CSS viewport 375×812 was reported; a screenshot is not treated as a CSS-pixel proof of composition. No Tesnova screenshot is stored in the repository.

### 10.7 Tablet — 768×1024

**Observed (Playwright only):**

- `innerWidth` 768, `innerHeight` 1024. CTAs remained side-by-side (same Y=796; widths 166 and 204). Not stacked.
- `scrollWidth` 966 (`overflowX` true). Page `scrollHeight` 16919 at this width.
- Toggle-menu control still present.

**Cursor cloud tablet emulation did not hold** the requested 768×1024 CSS size, so no Cursor tablet layout claim is made.

### 10.8 Reduced motion

**Observed after `prefers-reduced-motion: reduce` and homepage reload:**

- Playwright: `matchMedia` true; named `neon-gradient-move`, `pulse-glow`, and `float` animations were **absent**. `document.getAnimations()` reported 1 `CSSTransition`. Hero heading and “See our work” remained present.
- Cursor cloud: `matchMedia` true; `getAnimations()` reported 7 `CSSTransition` and no named neon/pulse/float animations.
- A full-viewport `canvas` remained present after the Playwright reduced-motion reload (1440×900 backing store). Whether the WebGL loop continued to paint was **not** measured.

**Limitations:** OS-level preference (not only DevTools emulation) was not used. Hover/scroll were not fully re-run under reduced motion. No claim that every decorative effect on the site honors the media query.

### 10.9 Performance implications

**Observed request/structure facts, not Lighthouse scores:**

- Playwright network log for the homepage included the HTML document, multiple `/_next/static` CSS/JS chunks, six `.woff2` fonts, Google Tag Manager `AW-18161295984`, Vercel insights, Prismic API/media, and a Tawk.to embed (`embed.tawk.to` plus follow-on widget scripts/CSS).
- Two sampled Prismic image responses were `image/avif` with `content-length` **31207** and **24381** bytes (URLs requested with large `w=` hints; transferred bytes are the observed sizes, not decoded bitmap size).
- At one desktop sample: 34 `document.images`, 50 `document.scripts`, one **WebGL2** canvas sized to the viewport (`pointer-events: none`), no `video` elements.
- Chat embed caused the document title to flicker to `1 new message` during the session.
- `Performance.getMetrics` in the Cursor cloud tab returned an empty metrics array. **No FPS, TTI, CLS, or Lighthouse numbers were captured.**

**Inference (not a measurement):** a full-viewport WebGL2 canvas plus looping CSS heading/glow/float animations plus a third-party chat embed is a plausible mid-range cost and a plausible explanation for the earlier `getExtension` failure in a different cloud session. That causal link is **not established**.

**Tessnova recommendation (product-specific, not a copy of this stack):** do not take a full-viewport WebGL background, looping heading gradients, 1500 ms `transition-all` headers, or third-party chat title mutation into Tattoo UI. Keep the existing rejections of cursor replacement, heavy parallax, scroll hijack, and motion-only status.

### 10.10 Observed fact versus inference versus hypothesis

| Category | Statement | Evidence / limit |
| --- | --- | --- |
| Observed fact | Homepage rendered usable content in both browsers on 2026-10-10; 2026-10-07 session did not. | Accessibility snapshots; UA/viewport `evaluate`; contrast with §9. |
| Observed fact | No custom global cursor replacement was found; hover on sampled CTA/card changed color or shadow without moving the target. | Computed style before/during/after hover. |
| Observed fact | Default motion included looping named CSS animations; reduced-motion emulation removed those named animations. | `document.getAnimations()` before vs after emulation+reload. |
| Observed fact | Tab moved through header/hero controls; some focused CTAs had `outline-style: none`; Escape did not dismiss the open bubble overlay. | Playwright keyboard sequence and overlay inspect. |
| Observed fact | Playwright mobile stacked the sampled CTA full-width; tablet kept CTAs in a row and showed horizontal `scrollWidth` overflow. | Geometry `evaluate`. |
| Observed fact | GitHub #10 is CLOSED; this document previously said keep it OPEN. | Live `gh issue view` vs §9.12. |
| Inference | Decorative enhancement on the reference is real and can be expensive. | Structure/network/animation counts; not a timed budget. |
| Unverified hypothesis | WebGL/`getExtension` caused the 2026-10-07 crash. | **Not established.** |
| Tessnova recommendation | Borrow craft threshold (legible hierarchy, recoverable hover, reduced-motion CSS halt) without copying identity, WebGL, overlay Escape failure, or agency CTAs. | Original product principle. |

### 10.11 Tattoo product cross-check

Preserve §§2–6 as **original Tessnova principles**. Runtime evidence did not authorize copying Tesnova.com. It also did not overturn approved Tattoo semantics.

| Approved Tattoo rule | Consequence after this observation |
| --- | --- |
| Books is request-intake status, never a public slot calendar. | Do not import agency “Book a 20-min call” / “Pitch a Project” funnels. OPEN/CLOSED must stay immediately textual. |
| Custom Request is qualification; ACCEPTED is not an appointment. | Overlay/chat patterns that steal focus or ignore Escape are unsafe on request/deposit surfaces. |
| Flash is scarce; one design cannot have two confirmed customers. | Looping decorative motion and testimonial marquees must not carry inventory meaning. |
| HOLD is temporary exclusive pending payment. | Reference hover polish is acceptable only as supplementary feedback; expiry remains text. |
| RESERVED / BOOKED are distinct. | Navigation transitions on the reference were ordinary route changes; they do not justify animated ownership claims. |
| Deposit amount/currency/policy precede payment. | Pricing-guide theatre on the reference is excluded as a template. |
| Private references stay private; public media requires permission. | Do not reuse Tesnova/Prismic imagery or chat-widget behavior. |
| Reduced motion and visible keyboard focus are Tessnova constraints regardless of the reference. | The reference *did* halt named CSS animations under emulation; several focused CTAs still used `outline-style: none`. Tessnova must not copy that focus gap onto money/scarcity controls. |

Ownership unchanged: Nova UI generic primitives/tokens; Tessnova Tattoo storefront composition and state behavior.

### 10.12 Issue #10 / M3 closure assessment

**Runtime matrix: recorded. M3 phase: not approved by this PR. Do not merge to `main` automatically. Do not auto-close or reopen issues.**

| Item | Live state after this session |
| --- | --- |
| Issue #10 | Already **CLOSED** by Founder 2026-10-07. This session fills the evidence gap the closed issue and §9 still described as missing. |
| Issue #37 | **CLOSED** with Founder design-direction approval. |
| Issue #1 | **OPEN**; body still said M3 is active while #10 is open. That sentence is stale versus GitHub issue states. |
| `AGENTS.md` | Still describes M2 as the current gate in the snapshot used for this work. Live GitHub #1 says M2 is complete and M3 is active. Surface, do not silently rewrite governance. |
| M4 / production | Still unauthorized. |

**Smallest recommended Founder actions after merge:**

1. Keep #10 closed unless the Founder wants a further Mac-native pass.
2. Edit Issue #1 so M3 is “active pending Founder M3 closure,” not “active because #10 is open.”
3. Explicitly approve or deny **M3 closure**. This PR must not be read as that approval.
4. Leave M4 unopened until that separate decision.

No Figma edits, no production code, no copied Tesnova assets.
