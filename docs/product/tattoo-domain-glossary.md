# Tattoo V1 — Canonical Domain Glossary

**Status:** Founder-approved terminology derived from Issue #12  
**Trigger:** Issue #20 — Trigger A  
**Source semantics:** `docs/product/tattoo-domain-semantics.md`

This glossary records **product language**, not database, API, enum or code identifiers.

If implementation naming later differs, the product meaning defined here remains authoritative unless a later Founder-approved product decision changes it.

Do not generalize these terms into cross-vertical platform language merely because another profession has something superficially similar.

---

## Books

The artist's current status for **new Custom Request intake**.

Books answers:

> Is this artist currently accepting new custom tattoo requests?

Books does **not** represent:

- appointment-slot availability;
- a public calendar;
- Flash availability;
- the state of an already-submitted request.

### Books Open

The artist is currently accepting new Custom Requests.

Product effects:

- new Custom Requests may be submitted;
- no appointment slot is implied;
- submission does not guarantee acceptance.

### Books Closed

The artist is not currently accepting new Custom Requests.

Product effects:

- new Custom Request submission is unavailable;
- already-submitted requests continue through their lifecycle;
- published Flash keeps its own independent state;
- no waitlist is created automatically.

An optional reopening date/note may be displayed, but it is informational only and does not automatically reopen Books.

---

## Guest Spot

An optional dated location notice associated with the artist's existing storefront.

Example:

> Amsterdam · 12–16 May

A Guest Spot:

- provides location/timing context;
- may coexist with Books Open or Closed;
- does not automatically override Books;
- does not promise appointment availability;
- does not create a second workspace, business or generic location engine.

If the artist wants to accept new Custom Requests for that period through the normal V1 flow, Books must be Open.

---

## Flash

A published **scarce tattoo design** that may have only one active exclusive customer at a time.

Flash is not just a portfolio/gallery image. It carries reservation state.

### Hard Flash invariant

> **One scarce Flash design must never have two confirmed customers.**

For the V1 reservation model, Flash is treated as scarce/single-customer inventory. Repeatable or unlimited Flash is not part of this contract.

---

## Available

A Flash design with no active hold and no confirmed reservation.

Product meaning:

- a client may attempt to claim it;
- only one claim may successfully acquire the exclusive hold.

Canonical product label:

**Available**

Implementation storage naming is not defined here.

---

## Hold Pending Payment

A temporary **exclusive** Flash claim for one client while the reservation-confirmation condition is being completed.

Product meaning:

- the Flash is unavailable to other clients during the hold;
- exactly one client owns the active hold;
- the hold is **not yet a confirmed reservation**;
- the hold must have a finite expiry.

The following are intentionally **not** defined here:

- what exact action starts the hold;
- hold duration;
- payment/deposit amount;
- payment-provider behavior.

Those belong to Issue #14.

Canonical product term:

**Hold Pending Payment**

---

## Reserved

A Flash design with exactly one **confirmed customer**, but without requiring a confirmed tattoo appointment yet.

Product meaning:

- no other customer may hold, reserve or book that design;
- reservation is exclusive;
- Reserved is distinct from Booked.

The exact deposit/payment condition required to reach Reserved belongs to Issue #14.

Canonical product label:

**Reserved**

---

## Booked

A Flash design whose reserved customer also has a **confirmed tattoo appointment** for that design.

Product meaning:

- the customer remains the single exclusive customer;
- the design remains unavailable to everyone else;
- Booked is the normal terminal state of the V1 Flash reservation lifecycle.

Canonical product label:

**Booked**

---

## Custom Request

A structured tattoo request submitted to a specific artist for qualification and assessment.

A Custom Request is a **lead/request**, not an appointment.

It does not by itself:

- reserve a date;
- guarantee artist acceptance;
- guarantee a final quote;
- guarantee a tattoo;
- create Flash reservation state.

### Required V1 qualification information

- placement;
- approximate size in centimetres;
- black / colour preference;
- one or more reference images;
- short description / idea;
- cover-up status;
- rough desired timing;
- reply contact.

Budget is optional in the V1 definition.

---

## Submitted

A Custom Request has been completed with the required information and sent to the artist.

No appointment or reservation exists.

---

## In Review

The artist is actively assessing a Custom Request.

No commitment has yet been made.

---

## Needs Info

The artist cannot yet make a basic qualification decision and has requested clarification or additional context.

Once the requester supplies the needed information, the request returns to In Review.

---

## Accepted Request

A Custom Request the artist has assessed and is willing to continue toward doing, based on the information currently available.

### Hard acceptance rule

> **Accepted Request is not automatically an appointment.**

Accepted does **not** mean:

- appointment booked;
- date reserved;
- final quote agreed;
- deposit paid;
- Flash reserved;
- tattoo unconditionally guaranteed.

Acceptance ends the **Custom Request qualification lifecycle**. Later scheduling/payment concepts remain separate.

Canonical product state:

**Accepted**

Canonical glossary phrase:

**Accepted Request**

---

## Declined

The artist has decided not to proceed with the Custom Request.

No appointment or reservation is created.

---

## Withdrawn

The requester has chosen not to continue before the artist accepts the request.

The Custom Request is no longer active.

---

## Deposit

A fixed monetary prepayment associated with specific tattoo work.

V1 product meaning:

- tied to one specific accepted Custom Request or specific Flash reservation;
- credited toward the final tattoo price;
- artist-facing rather than a generic Tessnova balance;
- separate from appointment state.

### Custom Request

A custom Deposit may be requested only after the Custom Request is **Accepted**.

Deposit payment does not automatically create an appointment.

### Flash

A public Flash reservation uses Deposit as the confirmation mechanism:

```text
AVAILABLE
  ↓ exclusive claim
HOLD PENDING PAYMENT
  ↓ deposit PAID while hold is active
RESERVED
  ↓ appointment confirmed
BOOKED
```

The V1 Flash hold lasts **15 minutes** from successful exclusive hold acquisition.

A payment confirmed after the hold has expired must never override current Flash state or create a second confirmed customer.

### Amount

The artist may configure separate fixed default amounts for:

- Custom Request Deposit;
- Flash Deposit.

V1 does not require percentage deposits or arbitrary per-request amount overrides.

### Financial state

```text
DUE → PAID → REFUNDED | RETAINED
```

A failed payment attempt remains DUE while the relevant payment opportunity is active.

### Cancellation

The artist owns the cancellation/refund policy.

V1 does not impose one universal refund window.

A paid cancellation ends with an explicit **Refunded** or **Retained** outcome.

Refund/cancellation never automatically re-releases scarce Flash; the artist must explicitly release the design.

### Ownership boundary

Tessnova may facilitate payment and record state, but the storefront/product must preserve the client-to-artist relationship rather than present Tessnova as the tattoo service provider.

Payment-provider and merchant architecture remain M4 decisions.

See `docs/product/tattoo-deposit-semantics.md` for the full Issue #14 contract.

---

# Canonical lifecycle summaries

## Books

```text
OPEN ↔ CLOSED
```

Artist-controlled.

No automatic calendar-driven transition in V1.

## Flash

```text
AVAILABLE
  ↓
HOLD PENDING PAYMENT
  ↓
RESERVED
  ↓
BOOKED
```

Expiry/release paths may return a Flash design to Available only under the approved transition rules.

## Custom Request

```text
SUBMITTED
  ↓
IN REVIEW
  ↔ NEEDS INFO
  ↓
ACCEPTED | DECLINED

WITHDRAWN may occur before acceptance.
```

---

# Cross-domain rules

1. **Books is status, not scheduling.**
2. **Books controls new Custom Request intake, not Flash availability.**
3. **Flash state belongs to the individual scarce design.**
4. **One scarce Flash design has at most one active exclusive customer.**
5. **A hold is exclusive but not confirmed.**
6. **Reserved does not require an appointment.**
7. **Booked requires an appointment.**
8. **Accepted Request is not automatically an appointment.**
9. **Custom Request acceptance does not create Flash state.**
10. **Closing Books does not invalidate existing requests.**
11. **Guest Spot is context, not a workspace/location engine.**
12. **Deposit/payment semantics remain bounded by Issue #14.**

---

# Naming discipline

These are Tattoo product terms.

Do not prematurely rename them to generic concepts such as:

- availability;
- inventory item;
- booking object;
- lead object;
- workflow status;
- reservation engine;
- vertical capability.

M4 may choose implementation identifiers, but those identifiers must preserve the Founder-approved product semantics rather than redefining them.
