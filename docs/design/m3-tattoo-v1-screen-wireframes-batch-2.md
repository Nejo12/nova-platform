# M3 Tattoo V1 — Responsive Screen Wireframes, Batch 2

**Status:** EDITABLE DESIGN DRAFT — awaits Founder review and user validation  
**Issue:** [#37 — Responsive Tattoo V1 screen wireframes and interaction-state variants](https://github.com/Nejo12/nova-platform/issues/37)  
**Canonical Figma page:** [M3 — Tattoo V1 Screen Wireframes · DRAFT #37](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=27-2)  
**Foundational approved flow:** [M3 Batch 1 / Issue #35](m3-tattoo-v1-flow-batch-1.md)  
**Product authority:** [Approved Tattoo V1 M2 scope](../product/tattoo-v1-approved-scope.md) and [NOT_NOW](../../NOT_NOW.md)

## 1. What is actually delivered

The canonical Figma file contains **nine native/editable low-fidelity frames** on its own clearly marked draft page `27:2`:

| Frame ID | Device / state | Purpose |
| --- | --- | --- |
| `27:3` | Mobile, 390px · artist setup | Private draft, name/city/style, original portfolio image placeholder, per-asset publication-right acknowledgement, explicit OPEN/CLOSED Books selection and preview |
| `27:36` | Mobile, 390px · Books OPEN storefront | Artist-work hierarchy, available new **Custom Request** CTA, no instant appointment language |
| `27:56` | Mobile, 390px · Books CLOSED storefront + Flash | New Custom Requests unavailable; eligible independent Flash available, policy/payment prerequisites |
| `27:78` | Mobile, 390px · Custom Request | Eight mandatory tattoo-specific inputs, optional budget, private references and no-appointment message |
| `27:126` | Mobile, 390px · Flash temporary hold | Single exclusive 15-minute HOLD_PENDING_PAYMENT, artist-set positive fixed credited Deposit/currency, artist policy before paying |
| `27:144` | Mobile, 390px · Flash RESERVED | Valid paid reservation **without a booked appointment**, status distinction |
| `27:161` | Mobile, 390px · expired Flash / late-payment exception | No re-claim after hold expiry, no second confirmed client, separate exception resolution |
| `27:175` | Mobile, 390px · Artist Home | Books, current requests, active Flash, payment exception and public-media rights controls |
| `27:197` | Desktop, 1280px · Books OPEN storefront | Responsive-composition **concept** for the same public product behavior, artwork-dominant editorial split and truthful request CTA |

These views are **wireframes**, not final Figma brand styles, actual responsive constraints/prototypes, verified mobile screenshots in a browser, validated interaction components, or executable payment/booking flows. Public portfolio imagery is deliberately marked as a **placeholder**. The example artist name, mock request counts and sample **80,00 €** are illustrative only—**not** real customers, portfolio rights, mandated prices or default currency.

### Structural and visual QA already performed

- The draft is a separate page. Previously approved M2 and Batch 1 Figma material was preserved.
- All nine frames consist of native editable Figma frames, text, layout and status placeholders.
- Widths: eight mobile frames **390px**; one desktop storefront **1280px**.
- First screenshot revealed a clipped desktop artwork row due to a 50px fixed cross-axis size. Fixed nested auto-layout `27:217` to grow with 135px artwork placeholders; verified new desktop height **640px**.
- A follow-up screenshot of frame `27:197` was visually inspected and confirmed un-clipped art tiles, artist headline, Books status, accessible textual CTA and disclaimers.
- The Figma page uses simple draft fills and framing for low-fidelity structure, **not** a transplanted Material/third-party design-system look. A product-specific visual system and actual Nova UI component inventory are later M3/M4 work.
- The screens are not yet wired into a clickable Figma prototype. **Static representation of nine states is not an interactive state machine or tested working behavior.**

## 2. Correctness map to approved Tattoo product rules

**Books** controls new Custom Requests only; a CLOSED artist may still offer separately AVAILABLE Flash. A Books label is not a slot calendar.

**Custom Request** is a qualification lead. Inputs: placement, approximate size **cm**, black/colour preference, at least one private reference, tattoo idea, cover-up yes/no, rough desired timing and reply contact. Budget is optional. Submission and even later **ACCEPTED** do not constitute appointment confirmation.

**Flash:** AVAILABLE → one exclusive **HOLD_PENDING_PAYMENT** for working **15 minutes** → **RESERVED** only after valid, in-hold Deposit success by the same holder. **BOOKED** requires separate appointment confirmation. Expiry/late payment cannot double-confirm a design. Cancellation needs REFUNDED/RETAINED disposition and explicit artist re-release. Figma shows representative hold/reserved/expiry states but does **not** yet implement real Figma transition interactions.

**Deposit:** fixed work-specific, artist-defined, *credited to final tattoo price*, with true amount/currency and understandable artist-approved German refund policy. **80,00 €** is only a labeled mock example. Do not interpret the preview as payment-provider/legal approval.

**Media/publication:** Only real artwork with a rights/identifiable-person publication declaration becomes eligible for public use. No real images or client references were uploaded for this draft. An acknowledgement text is not Tessnova independently obtaining the pictured person's GDPR consent. Actual removal/takedown flows are still screen-level follow-up.

**Initial locale:** German `de` system UI. These are **illustrative draft labels**, not reviewed legal notices, localized production copy or comprehensive bilingual UX.

**Accessibility:** State cues use readable words, not just color. The screens are not keyboard-enabled browser controls. M3 must specify focus, target size, form errors, responsive reflow, reduced-motion and accessible countdown announcement before visual design approval.

## 3. Gaps to address before an interactive/Figma-prototype sign-off

This is the **first responsive screen batch**, not closure of all Issue #37 acceptance conditions:

1. Add explicit Figma prototype links/interactions for Custom Request submitted/needs-info/accepted/declined, Flash reserved/expiry and error recovery, plus Books OPEN/CLOSED changes.
2. Add absent dedicated screens: artist preview and publish confirmation, media rights withdrawn/lost-last-image readiness, explicit successful booking (appointment separate from RESERVED), contested Flash hold (second client), failed payment retry while hold valid, refund/retain and explicit artist re-release.
3. Validate actual mobile/desktop responsive behavior at 375/390, 768 and 1280/1440 widths; two separately drawn widths are **not** proven responsive layout.
4. Design user-operable permission controls and private upload treatments, including German policy/legal review and full request privacy explanation.
5. Run real artist/client task comprehension testing: fast publish within under-10-minute hypothesis, required request completion, understanding of no appointment, no double-confirmed Flash and language suitability.
6. Create polished, distinctive **Tattoo-specific** storefront visual proposals only after Founder review of information and state design; do not copy the Tesnova.com reference site.
7. Issue #10's external interaction/browser audit remains independently open. This Figma batch does not resolve it.

## 4. Founder review requested

Please review the [Figma draft screen board](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=27-2) and specifically check:

- Is the first visual decision point focused on artist, authorized work, truthful Books and the correct next action?
- Are initial Custom-only setup and independent Books-CLOSED Flash understandable without false payment prerequisites?
- Do the client Request and Flash states avoid an appointment promise?
- Are the exceptional cases clear enough to prototype?
- Should the next bounded M3 batch prioritize **clickable safety/exception states** before polished Tattoo theme exploration?

Issue #37 remains **OPEN until the Founder explicitly approves the screen wireframes and any required revisions**. M3 is active; M4/M5 implementation, payment infrastructure, shared vertical engines and code deployment remain separately gated. Founder performs all PR merges manually.
