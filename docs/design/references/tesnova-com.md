# Design Reference — Tesnova.com · M3 Interaction-Quality Study

**Reference:** https://www.tesnova.com/  
**Status:** M3 research and original Tessnova design-direction proposal; **live interaction verification still pending**  
**Source of truth:** This document is the repository reference study for [Issue #10](https://github.com/Nejo12/nova-platform/issues/10).  
**Originally recorded:** 2026-10-06  
**Study date:** 2026-10-06  
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

Do **not** describe any of these as observed facts or claim that the reference meets accessibility/performance standards. Repeat this test in a browser-enabled environment (Founder/Claude Code Agent on Mac or Work browser) before marking Issue #10's observation portion complete. A screenshot of a static marketing asset is **not** equivalent to a measured interaction.

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

## 7. Required live-reference browser verification — OPEN

The following matrix must be completed in a browser-enabled environment **before Issue #10 is considered fully verified**. Capture timestamp, viewport and evidence; label the site itself as the **external reference**.

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

**Closure criterion:** if the Founder accepts the design principles **without** a runtime audit, Issue #10 can be explicitly scoped to a principles-only study by a new Founder decision; otherwise leave #10 open until this observational matrix is completed. A documentation PR with this proposed motion language does **not** imply that its reference behaviors were verified.

## 8. Founder review and M3 follow-on

- [ ] Confirm the desirable qualities: responsive feedback, visual rhythm, distinct editorial themes, truthful CTA, deliberate microinteractions.
- [ ] Reject global cursor trails, parallax-heavy pages, scroll hijack and automatic visual distraction by default.
- [ ] Confirm storefront-versus-product separation and no import of agency site content/identity.
- [ ] Approve *testing* the candidate motion range—not hard-coded production tokens.
- [ ] Confirm accessibility/reduced-motion, privacy and paid Flash semantics are gating design constraints.
- [ ] Keep live reference interaction verification explicit and unfinished, not mislabeled “studied and observed.”
- [ ] Keep #10 open until the live verification matrix or an explicit narrower Founder definition resolves the evidence gap.

**M3 deliverables after this reference:** user-flow and low-fidelity Tattoo prototype work in the canonical Tessnova Figma; independent artist/client research; visual theme exploration; approved interaction-spec and accessible states. No M4/production implementation is authorized.

---

*Research stance: preserve Founder intent; separate directly retrieved site structure, independently verified standards, unobserved behaviors, and original Tessnova design hypotheses.*
