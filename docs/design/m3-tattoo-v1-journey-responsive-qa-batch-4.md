# M3 Tattoo V1 — Journey, Responsive and Accessibility QA, Batch 4

**Status:** M3 DRAFT — editable Figma design/prototype evidence; **not** production code, browser accessibility evidence, legal review or participant-validation evidence  
**Issue:** [#37 — Tattoo V1 responsive screen wireframes and interaction-state variants](https://github.com/Nejo12/nova-platform/issues/37)  
**Canonical Figma:** [Batch 4 start frame `52:178`](https://www.figma.com/design/OQmqaRuqB7qE5X3LTJsq7J/?node-id=52-178) on page **M3 — Tattoo Journey + Responsive QA · DRAFT #37** (`52:177`)  
**Predecessors:** [Batch 2 responsive screen drafts](m3-tattoo-v1-screen-wireframes-batch-2.md), [Batch 3 clickable exception-state prototype](m3-tattoo-v1-clickable-exception-prototype-batch-3.md)  
**Product authority:** [Founder-approved Tattoo V1 scope](../product/tattoo-v1-approved-scope.md), [Tattoo domain semantics](../product/tattoo-domain-semantics.md), [Deposit semantics](../product/tattoo-deposit-semantics.md), [onboarding / Artist Home](../product/tattoo-onboarding-ai-artist-home.md), [public-media permission](../product/tattoo-public-media-permission.md), [German-first locale contract](../product/tattoo-initial-language-locale.md), [NOT_NOW](../../NOT_NOW.md).

## 1. Bounded Batch 4 outcome

Batch 4 extends Issue #37 without reopening approved M2 product semantics.

A new separate native/editable Figma page contains **16 top-level frames** covering:

- a Batch 4 prototype entry screen;
- public storefront QA at **375px**, **768px** and **1440px**;
- Custom Request blank, validation-error and ready-to-submit states;
- reference-upload failure and recovery;
- submitted Custom Request confirmation;
- Artist Home Books OPEN, close-confirmation and CLOSED states;
- public-media permission, removal-confirmation and not-ready states;
- an explicit accessibility / interaction QA board.

The page contains **22 real Figma click reactions** with **zero broken destinations**.

No existing M2 material or earlier M3 Batch 1–3 page was overwritten.

## 2. Nova UI / Tessnova boundary

The screens use generic **Nova UI Button and Text Input primitives** for generic controls. The Tattoo-specific composition, state explanations, Books behavior, Custom Request qualification, media-permission behavior and storefront composition remain Tessnova-owned product UI.

The page currently contains **40 component instances** across the generic controls.

This is design evidence only. It does not create or modify Nova UI production packages or establish a new shared product abstraction.

## 3. Custom Request journey

The Custom Request form includes the approved Tattoo qualification contract:

1. body placement;
2. approximate size in centimetres;
3. black / colour preference;
4. one or more reference images;
5. short tattoo idea / description;
6. cover-up yes/no;
7. rough desired timing;
8. reply contact;
9. optional budget.

The draft explicitly preserves:

- a Custom Request is a qualification lead, not an appointment;
- reference images remain private and do not become public portfolio/Flash media automatically;
- budget remains optional;
- no public slot picker is introduced.

### Validation path

The clickable path is:

`blank → validation errors → ready → submitted`

The validation state uses:

- field-level messages adjacent to the affected field;
- a visible error summary;
- wording as well as visual treatment, rather than colour-only error meaning.

The submitted state states that the request is **not** an appointment, quote or payment confirmation.

### Upload failure path

The ready form can branch to a reference-image upload failure.

The failure state communicates that:

- the local selection should not be silently discarded;
- the user can retry;
- the upload remains private;
- the request is not submitted until the required validation/upload path succeeds.

This is representational design behavior. There is no real upload, persistence, retry transport or private-data processing in Figma.

## 4. Books state-change path

The artist-facing prototype includes:

`BOOKS OPEN → close confirmation → BOOKS CLOSED → reopen simulation`

The confirmation explicitly says closing Books:

- stops **new Custom Requests**;
- does not delete or auto-decline existing requests;
- does not change Flash availability automatically;
- does not create a public calendar.

The CLOSED state keeps Flash lifecycle truth separate.

No scheduling/availability engine is introduced.

## 5. Public-media permission path

The clickable media path is:

`publicly authorized → removal confirmation → public image removed / profile not ready`

The design preserves these boundaries:

- Custom Request reference media is separate and private;
- withdrawing public display removes the affected public image;
- media withdrawal does not silently release a RESERVED/BOOKED Flash;
- media withdrawal does not automatically refund a Deposit;
- removal of the last authorized public image may make the storefront no longer publishable.

No legal consent system, storage schema, rights database or moderation engine is implied.

## 6. Responsive QA

The new storefront specimens add fixed design review widths that complement the existing Batch 2 screens:

| Width | Review intent |
| --- | --- |
| 375px | narrow mobile composition and full-width primary action |
| 390px | interaction/form/artist-state specimens |
| 768px | tablet composition and side-by-side action hierarchy |
| 1280px | existing Batch 2 desktop specimen |
| 1440px | wide desktop composition with bounded content hierarchy |

The designs preserve the same semantic order across sizes:

`identity → Books → authorized work → eligible Flash → next action`

The fixed Figma widths do **not** prove real CSS reflow, browser zoom, text enlargement or device behavior.

## 7. Accessibility / interaction contract captured

The Batch 4 QA board records design requirements for later executable verification:

- Nova UI medium controls provide a 48px control height in these specimens;
- status and validation meaning must not rely on colour alone;
- error summary plus field-level errors are required;
- confirmation UI must later implement focus entry, appropriate trapping/dismissal and focus restoration;
- reduced-motion users must not depend on the prototype's 120ms dissolve;
- real keyboard tab order, screen-reader announcements and timed Flash hold live-region behavior remain unverified.

Figma native clicks are **not** accessibility-test evidence.

## 8. Independent verification performed

The delivered Figma page was read back after creation.

Verified structurally:

- page `52:177` exists under the expected DRAFT name;
- **16 top-level frames** exist;
- storefront widths are exactly **375**, **768** and **1440** where specified;
- mobile interaction/form states are 390px;
- **22 native reactions** resolve to existing destination nodes;
- **0 broken destinations**;
- all eight mandatory Custom Request inputs plus optional budget are present;
- generic Button/Text Input instances are present.

Verified visually with rendered screenshots:

- Batch 4 entry;
- Custom Request validation-error state;
- Custom Request ready state;
- Books-close confirmation;
- 768px storefront;
- 1440px storefront;
- accessibility / interaction QA board.

A visual overlap in the reference-upload helper copy was found during QA and corrected before this documentation was written. A mixed-English desktop phrase was also corrected to preserve the German-first draft direction.

## 9. What remains unverified / outside this batch

Issue #37 must remain open.

This batch does **not** provide evidence for:

- participant usability or comprehension testing;
- Founder final design approval;
- real responsive browser/CSS behavior;
- real keyboard/screen-reader behavior;
- accessible live countdown/expiry announcement;
- legally reviewed German payment/privacy/cancellation copy;
- real payment, hold, concurrency or reservation behavior;
- real media-rights enforcement or data processing;
- M4 architecture;
- production implementation.

Issue #10's remaining reference-site live-browser research also remains separate.

## 10. Founder review gate

Review the Batch 4 Figma page from frame `52:178`.

A Founder merge of the documentation PR records this **draft design/QA artifact only**. It does not approve M4, M5, production implementation, legal wording, accessibility conformance or participant-validation success.

Keep Issue #37 open until the Founder explicitly approves the design direction and decides whether the remaining M3 validation gaps are sufficient to close or require another bounded design/research batch.
