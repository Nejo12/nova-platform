# M2 — Product Definition

**Status:** ACTIVE  
**Launch vertical:** Tattoo

## Objective

Define a narrow, evidence-backed Tattoo V1 before technical architecture or implementation.

## Product thesis

Tessnova V1 is not a generic website builder.

It is a professional bio-link/storefront and structured booking-request workflow for independent tattoo artists.

The public page gets attention out of Instagram DMs. The workflow is what creates retained value.

## Candidate V1 loop

```text
ARTIST
  ↓
Onboarding
  ↓
Profile + portfolio + flash + books status
  ↓
Publish Tessnova link

CLIENT
  ↓
View work / books / flash
  ↓
Custom request OR flash reservation
  ↓
Deposit where applicable

ARTIST HOME
  ↓
Books
New requests
Flash holds
Deposits
```

## M2 decisions required

1. Primary ICP
2. Jobs-to-be-done
3. V1 success metrics
4. Books domain semantics
5. Flash state machine
6. Custom Request schema and states
7. Deposit semantics and ownership
8. Public storefront information architecture
9. Artist Home information architecture
10. Onboarding inputs and generated outputs
11. Privacy / media-permission requirements
12. Initial locale requirement
13. P0 / P1 / postponed scope
14. Events paper stress-test
15. M2 approval gate

## M2 non-goal

Do not choose framework, database schema, payment architecture or production deployment here unless a product decision depends on it.

Those belong in M4 — Technical Architecture.
