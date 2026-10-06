# Tattoo V1 — Deposit Semantics and Payment Product Boundary

**Status:** M2 definition for Founder approval  
**Issue:** #14  
**Scope:** Product meaning of deposits, their relationship to Flash and Custom Requests, hold timing, cancellation/refund semantics, and client-facing ownership. This document does not choose a payment provider, merchant-of-record architecture, Stripe Connect model, database schema, or production payment implementation.

## 1. Evidence and approved inputs

This definition is grounded in:

- TAT-01;
- TAT-02;
- Founder-approved Issue #11 ICP/JTBD/success metrics;
- Founder-approved Issue #12 Books / Flash / Custom Request semantics;
- the canonical Tattoo glossary;
- Founder-approved Issue #13 storefront IA/theme contract;
- the approved M2 Product Definition frame in Figma.

### Research evidence

Both Tattoo participants currently use PayPal deposits as part of a manual artist-owned workflow.

TAT-01:

- custom deposit: EUR 80;
- Flash deposit: EUR 50;
- deposit credited to final tattoo price;
- non-refundable inside 48 hours of appointment;
- current payment is not tied to the booking/date;
- rejects clients feeling like they are paying "the platform".

TAT-02:

- uses a EUR 50 PayPal deposit;
- uses deposit to reduce no-show cost;
- current workflow agrees date, then takes deposit;
- no evidence was provided for a universal cancellation window or refund rule.

### Evidence boundary

Repeated evidence supports:

- deposits are normal in the observed Tattoo workflow;
- fixed monetary amounts are currently used;
- artist/customer ownership should remain artist-facing;
- payment should be tied to the specific work rather than an unstructured transfer.

Evidence does **not** establish:

- one universal deposit amount;
- one universal cancellation/refund window;
- one payment provider;
- one merchant architecture;
- that all artists sequence appointment confirmation and deposit in the same order.

Those gaps are resolved below as narrow M2 product decisions or explicit hypotheses.

---

# 2. Canonical V1 meaning of "Deposit"

A Tessnova Tattoo V1 **Deposit** is:

> A fixed monetary prepayment made toward a specific accepted Custom Request or specific Flash reservation, used to secure commitment with the artist and credited toward the final tattoo price.

The deposit is:

- associated with one specific piece of intended tattoo work;
- artist-facing, not a generic Tessnova balance;
- a partial prepayment, not an additional platform booking fee;
- credited toward the final tattoo price if the tattoo proceeds.

## Hard deposit rule

> **A V1 Deposit is credited toward the final tattoo price.**

Tessnova V1 does not support a separate non-crediting "reservation fee" semantic under the Deposit label.

If future evidence shows artists need a non-crediting fee, that requires a separate Founder-approved product decision rather than silently changing Deposit semantics.

---

# 3. Artist-owned customer relationship

The product must present the tattoo transaction as a relationship between the **client and artist**.

Client-facing language should communicate concepts such as:

- deposit for work with the artist;
- deposit to reserve a specific Flash design;
- deposit toward an accepted custom tattoo.

It must not imply that Tessnova:

- is selling the tattoo;
- owns the booking relationship;
- is the tattoo service provider;
- owns the artist's client.

Tessnova may facilitate payment, state and record-keeping.

## M4 architecture constraint

M4 may select payment infrastructure only if it can preserve this product meaning and legal/client-facing presentation.

If a provider or merchant architecture would require Tessnova to present itself materially differently, that is a product/architecture conflict and must be surfaced before implementation.

Issue #14 does **not** choose the provider or merchant architecture.

---

# 4. Amount configuration

V1 uses **fixed monetary amounts**, not percentage-based deposits.

## Separate artist defaults

The artist may configure separate default deposit amounts for:

1. **Custom Request deposit**
2. **Flash deposit**

This is supported by TAT-01 using different custom and Flash amounts.

A single universal artist deposit amount is therefore not sufficient as the V1 product contract.

## Custom Request amount

The configured Custom Request amount is the default amount the artist may request after accepting a Custom Request.

The artist is not required to request a deposit on every accepted Custom Request.

V1 does not require arbitrary per-request deposit overrides as a product requirement. M3 may test whether such flexibility is materially needed.

## Flash amount

A client-facing Flash reservation path that uses Tessnova's public reservation flow requires a positive configured Flash deposit.

The deposit amount must be shown before the client commits to payment.

V1 does not define percentage deposits.

## Currency boundary

The amount must be shown with an explicit currency.

The supported locale/currency strategy remains a separate M2 closure input and later M4 implementation decision.

---

# 5. Deposit financial state

Deposit state remains separate from:

- Custom Request state;
- Flash reservation state;
- appointment state.

The V1 financial lifecycle is:

```text
DUE
  ↓
PAID
  ↓
REFUNDED | RETAINED
```

## DUE

Meaning:

> A specific deposit amount has been presented for specific work and successful payment is still required.

Payment failure does not create a new durable product state.

A failed attempt remains **DUE** while the relevant payment opportunity remains active.

## PAID

Meaning:

> The required deposit has been successfully received for the specific work.

PAID does not automatically mean:

- appointment booked;
- date confirmed;
- tattoo completed;
- final balance paid.

## REFUNDED

Meaning:

> A previously paid deposit has been returned to the client.

## RETAINED

Meaning:

> A previously paid deposit is kept by the artist after cancellation, no-show or another policy-defined outcome.

REFUNDED and RETAINED are mutually exclusive final deposit dispositions for the V1 product model.

V1 does not require partial-refund semantics.

---

# 6. Flash deposit contract

Flash uses Deposit as the confirmation mechanism for the client-facing reservation path.

## 6.1 Hold acquisition

A Flash design begins **Hold Pending Payment** when:

1. the design is currently AVAILABLE;
2. a client explicitly chooses to reserve/claim it;
3. Tessnova successfully grants that client the single exclusive hold.

The hold begins **before** the client completes payment.

This ordering is required to prevent two clients from paying for the same scarce Flash design.

## 6.2 Hold duration

V1 working rule:

> **A Flash hold lasts 15 minutes from successful hold acquisition.**

The duration is:

- fixed by the product in V1;
- not artist-configurable;
- shown clearly to the holding client;
- a product hypothesis to validate in M3.

The purpose is to give a serious client enough time to complete the deposit while preventing scarce Flash from being locked indefinitely.

## 6.3 During the hold

While a client owns the active hold:

- no second active hold may be granted;
- no other client may reserve the design;
- the client may retry a failed payment while time remains;
- the Flash design is not yet RESERVED.

## 6.4 Successful payment

A successful Flash deposit transitions:

```text
HOLD_PENDING_PAYMENT + deposit PAID
        ↓
RESERVED
```

This transition is valid only if the paying client still owns the active hold when the successful payment is confirmed.

RESERVED means:

- one confirmed customer owns the exclusive reservation;
- the design is unavailable to everyone else;
- an appointment date does not yet have to exist.

Later appointment confirmation changes Flash from RESERVED to BOOKED.

## 6.5 Hold expiry

If the Flash deposit has not successfully reached PAID before the 15-minute hold expires:

```text
HOLD_PENDING_PAYMENT
        ↓
AVAILABLE
```

The client loses exclusivity.

The design may then be claimed by another client.

## 6.6 Late payment safety rule

A payment confirmed **after the client's exclusive hold has expired** must never silently reclaim or reserve the design.

Hard rule:

> **Late payment cannot override the current Flash reservation state.**

If a late payment occurs after the design has become Available, entered another hold, or become Reserved/Booked for someone else:

- the payment is an exception requiring resolution;
- it must not create a second confirmed customer;
- the Flash invariant takes precedence over payment timing.

M4 must choose infrastructure that can safely detect and resolve this case.

---

# 7. Custom Request deposit contract

A Custom Request deposit behaves differently from Flash because Custom Request is qualification, not scarce inventory.

## 7.1 When a deposit may be requested

A Custom Request deposit may be requested only after the request is **ACCEPTED**.

A deposit must not be requested while the request is:

- SUBMITTED;
- IN_REVIEW;
- NEEDS_INFO;
- DECLINED;
- WITHDRAWN.

This preserves the approved rule that qualification happens before financial commitment.

## 7.2 Accepted does not mean deposit paid

The Custom Request remains **ACCEPTED** whether the deposit is:

- not requested;
- DUE;
- PAID;
- later REFUNDED or RETAINED.

Custom Request state and Deposit state are intentionally separate.

## 7.3 Successful payment

For an accepted Custom Request:

```text
ACCEPTED + deposit DUE
        ↓
ACCEPTED + deposit PAID
```

Successful payment means:

> The client has made the agreed monetary commitment toward that specific accepted custom tattoo.

It does **not** automatically mean:

- appointment booked;
- date reserved;
- final quote locked;
- tattoo completed.

## 7.4 Appointment ordering remains flexible

Research shows different manual sequencing:

- TAT-01: quote → deposit → calendar date;
- TAT-02: date agreed → deposit → calendar.

V1 must therefore not force one universal order between:

- accepted custom work;
- appointment/date confirmation;
- deposit payment.

The product must keep those concepts distinct.

---

# 8. Cancellation and refund semantics

V1 does not hard-code one universal cancellation/refund window.

TAT-01 uses a 48-hour non-refundable rule, but this is single-participant evidence.

## Artist policy

The artist owns the cancellation/refund policy.

Before payment, the client must be able to understand the applicable policy sufficiently to know when the deposit may be:

- refunded;
- retained.

M3 defines the exact presentation.

## Cancellation outcome

When paid work is cancelled or abandoned, the deposit must end in an explicit disposition:

- **REFUNDED**, or
- **RETAINED**.

The product must not leave the financial outcome ambiguous.

## No automatic policy invention

Tessnova V1 does not automatically impose:

- 24-hour rule;
- 48-hour rule;
- 72-hour rule;
- percentage forfeiture;
- partial refund.

Those would require stronger evidence or later product approval.

---

# 9. Flash cancellation/release rule

For paid Flash:

> **Refund/cancellation does not automatically make the Flash design Available.**

After a RESERVED or BOOKED Flash cancellation:

1. the deposit disposition must be resolved as REFUNDED or RETAINED;
2. the artist must explicitly decide to release the design;
3. only then may the design return to AVAILABLE.

This prevents accidental resale when the artist may consider the artwork altered, consumed, unsuitable for resale, or otherwise unavailable.

The product must never infer release merely because money was refunded.

---

# 10. Custom Request cancellation rule

For an accepted Custom Request:

- refund/retention does not rewrite the historical qualification result;
- the request remains an Accepted Request record;
- deposit disposition is recorded separately.

Issue #14 does not create a new generic CRM/cancellation pipeline.

If later workflow needs a separate post-acceptance engagement/cancellation state, that must be defined explicitly rather than overloading Custom Request state.

---

# 11. Final tattoo payment boundary

Tessnova Tattoo V1 Deposit semantics do not require Tessnova to process the final tattoo balance.

The approved V1 meaning is:

> The deposit amount is credited toward the final tattoo price.

The remaining balance may be settled outside Tessnova unless a later approved scope expands payment handling.

Therefore Issue #14 does not introduce:

- final checkout;
- invoice engine;
- tipping;
- instalments;
- tax handling;
- full point-of-sale flow.

---

# 12. Product invariants

The following must remain true through M3 and M4:

1. **Every Deposit is tied to specific tattoo work.**
2. **A Deposit is credited toward the final tattoo price.**
3. **Tessnova must not present itself as the tattoo service provider.**
4. **Custom Request must be ACCEPTED before a custom Deposit may be requested.**
5. **Custom Deposit payment does not automatically create an appointment.**
6. **Flash hold starts before payment so scarce inventory becomes exclusive first.**
7. **Only one client may own an active Flash hold.**
8. **Flash payment creates RESERVED only while that client still owns the active hold.**
9. **Late payment can never create a second confirmed Flash customer.**
10. **Flash RESERVED does not require an appointment.**
11. **Flash BOOKED requires an appointment.**
12. **Cancellation/refund never silently re-releases Flash.**
13. **Paid cancellation ends with an explicit REFUNDED or RETAINED deposit disposition.**
14. **Cancellation policy is artist-owned; V1 does not impose a universal refund window.**
15. **Payment-provider architecture must preserve these semantics rather than redefine them.**

---

# 13. Client-facing clarity requirements

Before paying, the client must be able to understand:

- which artist/work the deposit applies to;
- deposit amount and currency;
- that it is credited toward the final tattoo price;
- whether they are securing a Flash design or paying toward an accepted Custom Request;
- the relevant cancellation/refund policy;
- for Flash, that the hold is temporary until successful payment;
- for Custom Request, that payment does not by itself guarantee an appointment.

Exact copy and UI belong to M3.

---

# 14. M3 validation questions

M3 should test:

1. whether clients understand Deposit as artist-facing rather than "paying Tessnova";
2. whether the difference between Flash hold, Flash Reserved and appointment Booked is clear;
3. whether a 15-minute Flash hold is enough time without feeling stressful;
4. whether a 15-minute hold creates excessive artificial scarcity or abandonment;
5. whether clients understand Custom Request ACCEPTED + Deposit PAID still does not automatically mean appointment booked;
6. whether separate Custom and Flash deposit amounts match artist expectations;
7. whether showing the deposit as credited toward final price removes ambiguity;
8. whether artist-defined cancellation policy can be explained concisely before payment;
9. whether artists need per-request Custom deposit override badly enough to justify added V1 complexity.

The 15-minute duration and no-per-request-override rule are product hypotheses, not M1 evidence.

---

# 15. Deliberately deferred to M4

Issue #14 does **not** choose:

- Stripe;
- Stripe Connect;
- PayPal;
- Adyen;
- payment service provider;
- merchant of record;
- connected-account architecture;
- payout schedule;
- fee model;
- webhook implementation;
- idempotency mechanism;
- database/payment schema;
- chargeback/dispute implementation;
- reconciliation implementation.

M4 must map the approved product semantics onto payment infrastructure.

If a provider choice conflicts with the artist-owned presentation or Flash invariant, surface the conflict before implementation.

---

# 16. Deliberately deferred elsewhere

Issue #14 does not decide:

## Issue #15

- where deposit controls live in onboarding;
- Artist Home deposit management UI;
- notification behavior;
- AI-generated policy text.

## Separate M2 closure inputs

- media-publication permission;
- initial locale/language/currency support.

## M3

- exact checkout/payment UI;
- timer visual treatment;
- client policy copy;
- refund/retain controls;
- appointment UI.

---

# 17. Issue #14 closure test

Issue #14 is complete when the Founder approves:

- canonical Deposit meaning;
- Deposit credited-to-final-price rule;
- artist-owned client/payment presentation;
- separate Custom and Flash amount defaults;
- Custom deposit timing;
- Flash hold start;
- 15-minute Flash hold rule;
- successful-payment transitions;
- late-payment safety rule;
- artist-owned refund/cancellation policy boundary;
- REFUNDED / RETAINED disposition;
- no automatic Flash release after cancellation;
- explicit M4 payment-architecture boundary.

Founder approval of #14 advances M2 to Issue #15.

It does **not** authorize production implementation.
