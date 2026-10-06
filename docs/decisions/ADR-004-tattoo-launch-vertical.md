# ADR-004 — Select Tattoo as Tessnova's first launch vertical

**Status:** Accepted — Founder approved  
**Date:** 2026-10-06

## Decision

Tessnova will define and design its first commercial product for **independent tattoo artists**.

Wedding / Events remains the preferred second-vertical stress test.

Professional Speakers remains a later opportunity.

## Evidence

The decision is based on two independent interviews per candidate vertical:

- TAT-01 — Berlin fine-line artist
- TAT-02 — Leipzig fine-line / botanical artist
- EVT-01 — Berlin / Brandenburg wedding florist
- EVT-02 — Hamburg wedding / event florist
- SPK-01 — product / engineering leadership speaker
- SPK-02 — leadership / team-resilience speaker

## Why Tattoo

Tattoo produced the strongest combination of:

- repeated workflow pain;
- direct reachability through Instagram;
- strong one-page / bio-link fit;
- clear willingness to pay;
- a narrow V1 that can be useful without becoming a broad business suite;
- stateful differentiation that generic site builders do not solve.

Both tattoo participants independently reported:

- serious enquiries mixed with social inbox noise;
- repeated qualification around placement, size and references;
- books-open / closed communication failing to stop DMs;
- PayPal-based deposits;
- manual flash claim state;
- **flash double-booking occurring twice**;
- rejection of generic-looking artist pages.

## Product wedge

The first Tessnova product should test this loop:

```text
Instagram / social discovery
        ↓
Tessnova bio link
        ↓
Work + books status + flash
        ↓
Custom request OR flash reservation
        ↓
Deposit
        ↓
Artist home
```

The page is the acquisition surface. The structured request / reservation workflow is the retained product value.

## Architecture consequence

This ADR does **not** authorize a generic multi-vertical framework.

For V1:

- use tattoo terminology;
- model tattoo rules directly;
- keep product-specific components local to Tessnova;
- generalize only after a second real vertical demonstrates the same contract.

The conceptual distinction between infrastructure, reusable capability and vertical rule remains useful, but must not force premature package/schema abstractions.

## M2 gate

M2 must define and approve:

- target customer;
- jobs-to-be-done;
- V1 user journeys;
- Books semantics;
- Flash state machine;
- Custom Request semantics;
- Deposit semantics;
- Artist Home requirements;
- onboarding;
- success metrics;
- non-goals.

No production implementation begins until the M2 Product Definition is approved.
