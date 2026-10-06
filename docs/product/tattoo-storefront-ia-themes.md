# Tattoo V1 — Storefront Information Architecture and Theme Principles

**Status:** M2 definition for Founder approval  
**Issue:** #13  
**Scope:** Public Tattoo storefront information architecture, content priority, theme contract and mobile-first constraints. This document does not define final visual design, motion language, production components, implementation architecture, onboarding controls, deposit/payment semantics, or M3 prototype details.

## 1. Evidence and approved inputs

This definition is grounded in:

- TAT-01 and TAT-02;
- the M1 evidence synthesis;
- the Founder-approved Issue #11 ICP/JTBD/success definition;
- the Founder-approved Issue #12 Books / Flash / Custom Request semantics;
- the canonical Tattoo glossary;
- the approved M2 Product Definition frame in Figma.

### Repeated evidence

Both Tattoo participants independently reported:

- Instagram/social as a major discovery source;
- serious enquiries mixed into social inbox noise;
- desire for a better-than-Linktree public presence;
- rejection of generic/shared-looking artist pages;
- Books status needing to be visible;
- Flash being operationally important;
- repeated qualification questions before a request can be assessed.

Additional evidence:

- TAT-01 would replace the current bio link if clients could see work, minimum price and Books status, but not merely for a prettier Linktree.
- TAT-02 would switch if the experience looked better than Linktree and reduced low-quality price DMs.
- TAT-02 cares about own-domain capability, but evidence does not support making custom domain universal P0.

### Product interpretation

The storefront must do two things quickly:

1. let a prospective client decide whether the artist appears relevant/credible;
2. route that client into the correct Tattoo action without defaulting to an ambiguous DM.

A visually attractive page that does not improve this decision/action path is insufficient.

---

# 2. V1 storefront model

Tattoo V1 uses a **single public artist storefront** as the acquisition surface linked from Instagram/social.

The V1 default is a **one-page, mobile-first experience** with optional navigation/section shortcuts if M3 design needs them.

It is not:

- a generic website builder;
- a public marketplace profile;
- a multi-page CMS;
- a public appointment calendar;
- a freeform theme editor;
- a studio/team workspace.

The artist owns the customer relationship. The storefront should feel like the artist's professional surface, not a marketplace listing owned by Tessnova.

---

# 3. Information architecture

The canonical content hierarchy is:

```text
1. ARTIST IDENTITY + CURRENT DECISION STATE
       ↓
2. WORK / PORTFOLIO
       ↓
3. FLASH — when the artist publishes Flash
       ↓
4. ARTIST / STYLE / STUDIO CONTEXT
       ↓
5. PROCESS / POLICIES / BOOKING INSTRUCTIONS
       ↓
6. NEXT ACTION / CLOSE
```

Themes may express this hierarchy differently, but they must preserve the same decision priorities and product semantics.

---

# 4. Section 1 — Artist identity + current decision state

This is the first decision zone.

A prospective client should be able to understand, without scrolling through a long introduction:

- who the artist is;
- where they work;
- what style(s) they do;
- whether Books are Open or Closed;
- the correct next action.

## Required identity/status content

- artist or business display name;
- city;
- studio context when relevant;
- primary tattoo style(s);
- Books status.

## Contextual content

Where applicable:

- Guest Spot;
- future Books reopening date/note;
- optional price minimum / price floor.

## Primary action when Books are Open

A clear **Custom Request** action must be available.

The action communicates request/intake, not instant booking.

It must not imply:

- a date is available;
- the tattoo is accepted;
- an appointment is confirmed.

## Primary state when Books are Closed

When Books are Closed:

- Books Closed remains clearly visible;
- Custom Request submission is unavailable;
- optional reopening information may be shown;
- the interface must not invent a waitlist;
- Flash may remain separately available.

This means a storefront can legitimately communicate:

> Books Closed · Flash available

without contradiction.

## Price floor

A price minimum/floor is optional artist content.

Where shown, it exists to reduce obviously unsuitable enquiries and establish basic fit.

V1 does not require:

- a complete price list;
- dynamic pricing;
- quote calculation;
- pricing configurators.

---

# 5. Section 2 — Work / portfolio

Work is the primary credibility and fit surface.

It should appear early enough that a prospective client can quickly judge whether the artist's style matches what they want.

## Portfolio principles

- actual artist work is visually dominant;
- image treatment must support tattoo detail rather than decorate over it;
- portfolio content should not be reduced to tiny generic thumbnails by default;
- themes may vary crop, rhythm, scale and composition;
- content must remain understandable without hover interactions.

## Content model boundary

Issue #13 defines only public prioritization.

It does not define:

- upload/storage architecture;
- image processing implementation;
- portfolio media consent workflow;
- tagging/search architecture.

The required media-publication permission rule remains an M2 input for #17 and must be resolved separately.

---

# 6. Section 3 — Flash

The Flash section is conditional.

If the artist does not publish Flash, the storefront omits the section rather than rendering an empty generic module.

If Flash exists, it is a high-value Tattoo-specific surface and must not be treated as ordinary portfolio content.

## Public Flash priority

The section should prioritize **Available** Flash because that is the actionable client opportunity.

For any Flash design rendered publicly:

- its state must never be ambiguous;
- only Available Flash may expose a new claim/reservation action;
- Hold Pending Payment, Reserved and Booked states must not appear actionable;
- the public experience must never visually imply that one scarce design is simultaneously available to multiple clients.

An artist may later choose whether non-available designs remain published as past/claimed work; exact controls and visual treatment belong to M3/#15.

## Books interaction

Flash remains independent from Books.

Therefore:

- Books Open + Available Flash is valid;
- Books Closed + Available Flash is valid;
- Books Open + Reserved/Booked Flash is valid.

The storefront must not visually collapse these into one generic availability state.

---

# 7. Section 4 — Artist / style / studio context

After the prospective client has seen the work, the storefront may provide supporting context such as:

- short artist bio;
- style focus;
- studio name/context;
- city/location context;
- Guest Spot context where applicable;
- relevant trust/working-style information.

The page should not force a long founder-style biography before showing work.

The role of this section is confidence and fit, not content marketing volume.

---

# 8. Section 5 — Process / policies / booking instructions

The storefront should make the request process legible before a client submits.

Candidate content includes:

- what the artist needs in a Custom Request;
- approximate response expectations where the artist chooses to state them;
- high-level tattoo/request policy;
- cancellation/rescheduling policy where appropriate;
- minimum price where not already shown;
- deposit explanation once #14 defines it.

## Deposit boundary

Until Issue #14 is approved, storefront copy must not imply exact:

- deposit amount;
- hold duration;
- refund conditions;
- payment provider;
- payment ownership model.

Issue #13 establishes only that the process/policies area is where approved client-facing deposit information may later appear.

---

# 9. Section 6 — Next action / close

The bottom of the storefront should leave the visitor with an unambiguous next step.

## Books Open

Repeat or preserve access to the **Custom Request** action.

The client should not have to scroll back to the top to understand how to proceed.

## Books Closed

Do not present a disabled/request-looking control that suggests submission is almost possible.

Instead:

- reinforce Books Closed;
- show reopening information when supplied;
- allow any separately available Flash path to remain actionable;
- preserve artist/social context without creating an unofficial waitlist.

## Supporting links

Social/contact links may be present as supporting artist identity/navigation.

They must not visually overpower the product's qualified request/Flash paths such that the storefront simply sends serious demand back into Instagram DMs.

---

# 10. Content priority rules

The storefront should optimize for **decision readiness**, not content completeness.

## Priority 1 — "Is this artist relevant and can I proceed?"

Surface early:

- artist identity;
- location/studio context;
- style;
- Books state;
- relevant action.

## Priority 2 — "Do I trust/want this artist's work?"

Surface prominently:

- portfolio;
- Flash where applicable.

## Priority 3 — "What should I know before I contact/request?"

Surface before or near final action:

- price floor where enabled;
- process;
- policies;
- booking/request instructions.

## Lower priority

Do not make these dominate V1:

- long biography;
- generic testimonials/carousels added only because websites often have them;
- blog/content-marketing sections;
- newsletter capture;
- generic service grids;
- unrelated social-feed widgets.

A future addition needs evidence rather than conventional website-builder expectations.

---

# 11. Theme contract

A Tessnova theme changes **presentation**, not Tattoo product semantics.

All themes consume the same structured artist data and preserve the same state/action meaning.

## Themes must vary materially

A valid theme may differ in:

- composition;
- section rhythm;
- density;
- typography;
- image scale/cropping treatment;
- spacing;
- background rhythm;
- emphasis and editorial hierarchy;
- navigation treatment;
- how portfolio and Flash are composed.

Changing only:

- accent colour;
- background colour;
- button radius;

does **not** constitute a meaningfully different theme.

## Themes must preserve

Every theme must keep:

- Books state understandable;
- Custom Request action semantics intact;
- Flash state integrity visible;
- artist identity clear;
- portfolio legible;
- mobile usability;
- keyboard/focus accessibility where interactive;
- reduced-motion fallback once motion is introduced;
- content/state meaning independent of hover.

## Theme safety rule

A theme must never make the product state less truthful for aesthetics.

Examples of invalid theme behavior:

- visually hiding Books Closed while presenting a strong "Book now" treatment;
- making Reserved Flash look Available;
- removing required action/state labels because they disrupt the composition;
- presenting Custom Request as an appointment booking action.

---

# 12. Theme customization boundary

V1 themes are **curated structured choices**, not a freeform page builder.

Do not introduce:

- arbitrary drag/drop page composition;
- section schema builder;
- custom CSS;
- generic component marketplace;
- per-field layout rules engine;
- unlimited font/spacing controls.

M3 may determine the smallest set of artist-facing choices that preserves individuality without creating a builder.

Possible bounded controls may later include choices such as theme, selected imagery and limited presentation preferences, but Issue #15/M3 owns the onboarding/editing experience.

---

# 13. Mobile-first constraints

Instagram/social traffic makes mobile the primary storefront context.

M3 designs must treat mobile as the starting point rather than a compressed desktop page.

## Required mobile behavior

1. The initial decision zone must communicate artist identity, location/style context, Books state and the correct next action without requiring extensive exploration.
2. Essential actions must be touch-friendly.
3. No product meaning may depend on hover.
4. Portfolio imagery must remain useful for judging tattoo work on a small screen.
5. Flash state and claimability must be readable without opening every item.
6. Custom Request must remain identifiable as a request, not a calendar booking.
7. Content ordering must work linearly when the layout collapses to one column.
8. Themes must tolerate variable artist names, bios, policy lengths and image aspect ratios without becoming visually broken.
9. Motion introduced during M3 must have reduced-motion behavior and must not block the primary action.
10. Visual richness must not require excessive media or interaction before the visitor can understand the artist and proceed.

Exact responsive breakpoints and implementation strategy belong later.

---

# 14. Visual quality principles

Visual credibility is a functional conversion requirement.

The storefront should feel:

- artist-led;
- deliberate;
- contemporary;
- premium enough to replace/add to a social bio link;
- visually distinctive without obscuring usability.

It should not feel:

- like a generic SaaS template;
- like identical profile cards with different colours;
- like an obvious AI-generated page;
- like a directory/marketplace listing;
- like a Linktree clone with extra fields.

## Tesnova.com boundary

Tesnova.com remains the permanent interaction-quality reference.

Issue #10 is an M3 task.

During M2/#13:

- preserve the quality bar;
- do not execute the detailed motion/interaction study yet;
- do not copy Tesnova.com's layouts, identity, assets or code.

M3 will derive Tessnova's own motion and interaction language.

---

# 15. Content/state matrix

| Content / action | Books Open | Books Closed | Conditional |
| --- | --- | --- | --- |
| Artist identity | Required | Required | — |
| City / studio context | Required | Required | Studio name only when relevant |
| Tattoo style(s) | Required | Required | — |
| Books state | Required | Required | — |
| Custom Request action | Enabled | Not available | — |
| Reopening note/date | Optional | Optional | Primarily useful when Closed |
| Guest Spot | Optional | Optional | Artist supplies it |
| Portfolio | Required | Required | — |
| Flash section | Independent | Independent | Only when artist publishes Flash |
| Flash claim action | Available Flash only | Available Flash only | Per Flash item state |
| Price floor | Optional | Optional | Artist chooses whether to show |
| Process/policies | Present where configured | Present where configured | Deposit wording waits for #14 |
| Supporting social links | Optional | Optional | Must remain secondary to qualified action paths |

---

# 16. M3 validation questions

M3 should test, rather than assume, whether:

1. an artist would actually place the storefront in their Instagram/social bio;
2. clients can identify artist/style/location/Books state quickly;
3. clients understand Custom Request as a request rather than instant booking;
4. Books Closed + Available Flash is understandable;
5. Available versus unavailable Flash is obvious without explanation;
6. portfolio composition feels distinctive enough to replace generic bio-link presentation;
7. materially different themes still feel like the same trustworthy Tessnova product;
8. theme variation creates artist individuality without requiring a freeform editor;
9. policy/process information appears early enough to prevent low-fit requests without overwhelming the page;
10. the one-page model remains sufficient for the primary Tattoo V1 acquisition job.

---

# 17. Deliberately deferred

Issue #13 does **not** decide:

## Issue #14

- deposit amount;
- payment/hold timing;
- refund/cancellation financial semantics;
- payment provider architecture.

## Issue #15

- exact theme-selection/editing UI;
- onboarding controls;
- AI copy-generation flow;
- Artist Home.

## Separate M2 closure inputs

- portfolio/media-publication permission rule;
- initial locale/language requirement.

## M3 / Issue #10

- exact visual compositions;
- final theme count;
- component styling;
- motion language;
- hover/pointer effects;
- transition choreography;
- prototype interactions.

## M4

- routing/framework;
- image pipeline;
- data model;
- storage;
- rendering architecture;
- performance implementation;
- responsive breakpoint implementation.

---

# 18. Issue #13 closure test

Issue #13 is complete when the Founder approves:

- the one-page public Tattoo storefront model;
- the canonical content hierarchy;
- public behavior for Books / Custom Request / Flash;
- content priority rules;
- theme principles;
- curated-theme versus freeform-builder boundary;
- mobile-first constraints;
- the explicit handoff to M3 for actual visual design.

Founder approval of #13 advances M2 to Issue #14.

It does **not** authorize production implementation.
