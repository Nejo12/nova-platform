# M3 Tattoo V1 — Clickable Exception-State Prototype, Batch 3

**Status:** M3 DRAFT — Figma clickable navigation exists; **no** live product transactions, measured timers, user test or production authorization  
**Issue:** [#37 — Tattoo responsive wireframes and interaction states](https://github.com/Nejo12/nova-platform/issues/37)  
**Canonical Figma:** [Prototype start screen, frame 30:3](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=30-3) on **M3 — Tattoo Exception-State Prototype · DRAFT #37** (page `30:2`). Open the frame in Figma and use **Present** to follow its native click prototype links.  
**Predecessor:** [Batch 1 approved flows](m3-tattoo-v1-flow-batch-1.md), [Batch 2 responsive screen drafts](m3-tattoo-v1-screen-wireframes-batch-2.md)  
**Product authority:** [Founder-approved Tattoo V1 scope](../product/tattoo-v1-approved-scope.md), [#12 domain contract](../product/tattoo-domain-semantics.md), [#14 deposits](../product/tattoo-deposit-semantics.md), [#15 artist onboarding](../product/tattoo-onboarding-ai-artist-home.md), [#28 public media permission](../product/tattoo-public-media-permission.md), [#29 initial language](../product/tattoo-initial-language-locale.md), [NOT_NOW](../../NOT_NOW.md).

## 1. Scope completed and independently verified

A **new separate editable Figma page** contains **21 mobile-width (390 px) state screens** connected by **39 Figma-native `ON_CLICK → NAVIGATE` reactions**, with Figma's real prototype entry point on frame **`30:3`**. No existing M2 designs, Batch 1 flow board or Batch 2 screen drafts were overwritten.

**Verification carried out against the actual Figma file:**

- Read back **21 screen frames**, **39 control frames**, **39 reaction edges**, and **zero missing destination nodes**; flow starting point resolves to `30:3`.
- Inspected actual rendered screenshots of entry, Flash hold and Artist IN_REVIEW frames for readable text, complete content and absence of visible clipping.
- Corrected Custom Request state-path drafting: **NEEDS_INFO → IN_REVIEW** when clarification is returned, not back to SUBMITTED, and removed two misleading direct response-to-terminal shortcuts.
- Used discreet `DISSOLVE` transitions (~120 ms), not copied animation from the reference site or a production motion-token commitment.
- Every state screen identifies itself as a **simulation / demo** with no real customer, backend hold clock, payment, reservation, appointment, rights grant or published image.
- No real tattoo art, actual customer references, private contact details, payment details or externally copied Tesnova.com material is included.

These are genuine Figma click navigations. They do **not** execute the application's domain rules and do not prove concurrent Flash integrity. A click labeled “Simuliere gültige Zahlung” is a manual walk-through of a hypothetical valid branch, **not** Stripe verification or a payment integration.

## 2. Clickable prototype flows

| Path | Frames / branch | What the reviewer must see |
| --- | --- | --- |
| Main entry | `START 30:3` | Explicit five scenario options and “no real backend” notice |
| Request entry | `REQUEST_SUBMITTED 30:21` → `IN_REVIEW 30:261` | Submitted = qualification lead, not appointment |
| Clarification | `IN_REVIEW` → `NEEDS_INFO 30:40` → `IN_REVIEW` | Clarification loop; the user may withdraw before ACCEPTED |
| Qualification completion | `IN_REVIEW` → `REQUEST_ACCEPTED 30:55` or `REQUEST_DECLINED 30:68`; preacceptance `WITHDRAWN 30:78` | ACCEPTED ≠ appointment, Deposit PAID or promised scheduling |
| Flash claim | `FLASH_HOLD 30:88` → `FLASH_RESERVED 30:117` | A single exclusive hold begins before payment; valid payment confirmed within the same hold reserves scarce artwork, not a tattoo appointment |
| Flash payment failure | `FLASH_HOLD` → `FLASH_RETRY 30:105` → hypothetical `FLASH_RESERVED` **only if original hold valid**; or `FLASH_EXPIRED 30:141` | Failure does not confirm; any retry must still be within the valid 15-minute hold |
| Hold expiry and second client | `FLASH_EXPIRED` → `FLASH_BLOCKED 30:153` | No automatic double confirmation; the “blocked” screen represents the second client while a new holder/confirmed owner exists, **not** permanent unavailability after expiry |
| Late payment | `FLASH_EXPIRED` → `FLASH_LATE 30:163` | A late-arriving payment cannot revive an expired claim or override a new holder; financial exception needs resolution |
| Appointment | `FLASH_RESERVED` → `FLASH_BOOKED 30:131` | BOOKED requires separate explicit appointment confirmation; the mock screen fabricates no agreed date |
| Paid cancellation | `FLASH_RESERVED` → `FLASH_CANCELLATION 30:176` → `FLASH_RELEASE 30:188` | Resolve REFUNDED/RETAINED then perform a separate artist release, not automatic return to AVAILABLE |
| Artist publication | `ARTIST_PREVIEW 30:198` → `ARTIST_PUBLISHED 30:213` | Authorized media, explicit Books and deliberate publish; live storefront is not automatically activated |
| Books CLOSED | `BOOKS_CLOSED 30:223` | Blocks new Custom Requests without cancelling existing work or independent AVAILABLE Flash |
| Media rights withdrawal | `MEDIA_WITHDRAW 30:236` → `MEDIA_NOT_READY 30:251` | A withdrawn public image stops being served; existing Flash holds/reservations/deposits do not silently reset; loss of last image impacts readiness |

**Navigation note:** Each screen has clickable prototype buttons. The screen copy is German-first, but this is **draft microcopy**, not vetted legal or payment terms.

## 3. What this prototype does *not* validate

Do **not** interpret clicking between states as implementation of:

- **15-minute elapsed-time enforcement**, a real countdown, timed automatic expiry or reliable server clock;
- a single atomic Flash holder, transaction locking, idempotent payment callbacks, concurrent customer sessions, ownership authorization, cancellation or refund execution;
- real form entry, upload, required-field validation or persisted client data;
- true responsive reflow across device widths or mobile browser quality—the clickable screens are 390px mock frames; Batch 2 contains a separate 1280px desktop design exploration;
- GDPR consent collection, artist's actual right to publicly display an image or processing legal basis;
- operational notification transport, screen-reader/keyboard behaviors, reduced-motion testing, German legal-text review or signed accessible production interaction contract;
- successful participant usability research or an M3 quality signoff.

**Explicit remaining risk:** The request prototype simulates several artist choices in one viewer/session. That is useful for review but not evidence of secure artist/client roles or permissions.

**Correct sequencing:** Flow design (M3) establishes conceptual behavior. M4 must select a safe architecture for multi-client transactions and privacy. M5 verifies executable product logic only after its separate Founder-authorized start.

## 4. Recommended structured M3 review

Using Figma's **Present** flow, ask an independent artist/client reviewer to walk through:

1. An initial Custom Request and one NEEDS_INFO clarification loop; ask whether ACCEPTED sounds like an appointment (it must not).
2. The Flash hold, valid simulated payment, RESERVED and separately BOOKED states. Ask for their interpretation of “a design reserved” versus “tattoo appointment booked.”
3. Failed payment followed by expiry; contrast with “retry while still valid.” Review copy for any impression the hold automatically extends.
4. A late payment after expiry while a different customer claims the design. Ask whether support resolution—not a second confirmed customer—is clear.
5. Paid cancellation. Ask who determines REFUNDED vs RETAINED and who can explicitly re-release the scarce Flash.
6. Books CLOSED and portfolio withdrawal while a Flash reservation exists. Verify no request-calendar or automatic financial release assumption.
7. Reduced-motion and keyboard/touch navigation **in later interactive design validation**; current native Figma click transitions alone are not a screen-reader test.

Record role (artist/client), comprehension, obstacles, any claims mistaken for appointment/financial outcomes, and actual task timing if measured. **No participants were tested in this batch**.

## 5. Outstanding M3 work before Issue #37 can close

- Founder inspection and explicit approval/revision of these 21 simulated exception states.
- Better complete onboarding → public storefront → Custom Request journey, with realistic form validation and privacy/failure UX prototypes.
- A clickable artist Books toggle and publisher permission withdrawal interaction **with safely separated state truth** (current design branches are representational).
- Mobile/tablet/desktop composition and reflow QA at 375/390, 768, 1280/1440; true focus, keyboard and reduced-motion equivalents.
- German legal/payment notice specialist review, accessible hold/expiry updates and actual owner-bound deposit/confirmation messaging.
- Research with representative artists/clients; validate approved #11 hypotheses without inventing results.
- Final visual-craft, differentiated curated Tattoo storefront themes after information/state quality review, never copying [Tesnova.com](references/tesnova-com.md). **Issue #10 browser reference observation remains open**.

## 6. Founder approval and merge semantics

This bounded docs PR records an **already-created editable Figma prototype** and its independently checked click topology. It does not approve screen aesthetics, product architecture, production code, generic shared runtime, external payments, actual media-publication permissions or M3 completion.

**Issue #37 remains OPEN** until the Founder explicitly approves the interaction direction and later work meets the issue's acceptance criteria. M4 and M5 remain gated. The Founder performs every merge manually; never merge or enable auto-merge by agent.
