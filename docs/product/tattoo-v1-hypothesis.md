# Tattoo V1 — Product Hypothesis

**Status:** M2 working hypothesis — not yet approved V1 specification

Issue #11 customer/outcome definition:
`docs/product/tattoo-v1-icp-jtbd-success.md`

## Target customer hypothesis

Primary ICP:

**Independent tattoo artists who own the client relationship, receive meaningful inbound interest through Instagram/social/referrals, and still qualify/manage that demand through fragmented manual tools.**

Typical fit includes:

- solo independent artists and chair renters;
- enquiry handling through DMs/email/WhatsApp;
- manual qualification around placement, size, references and related details;
- artist-controlled Books status and client communication;
- manual deposit handling;
- desire for a distinctive professional presence rather than a generic template.

Artists who also sell scarce flash are a particularly strong early-adopter signal because reservation integrity is a repeated high-severity pain, but Flash is not mandatory for every V1 customer.

Multi-artist studio/team management, marketplace-first buyers, and full public-calendar buyers are outside the primary V1 ICP.

See `docs/product/tattoo-v1-icp-jtbd-success.md` for the evidence, explicit exclusions and M3 validation assumptions.

## Core customer job

**Turn social attention into qualified tattoo work without losing serious enquiries, repeating the same questions, or double-selling scarce flash.**

Top jobs are:

1. convert social discovery into a credible next action;
2. qualify custom tattoo demand before manual conversation;
3. keep serious enquiries out of social inbox noise;
4. reserve scarce flash without double-confirming it;
5. tie commitment to the specific request/design while preserving the artist-owned customer relationship.

## Candidate P0 areas

### Public storefront
- artist identity
- city / studio context
- portfolio
- tattoo styles
- minimum / price floor where artist chooses to show it
- books status
- flash
- policies / booking instructions
- custom request entry point

### Books
- open
- closed
- optional guest-spot note

Books is not a calendar.

### Custom request
Required candidate fields:
- placement
- size in centimetres
- reference images
- black / colour
- description
- cover-up status
- rough month / timing

Budget remains configurable / optional pending further product definition.

### Flash
Candidate states:
- available
- hold pending payment
- reserved
- booked

The product must prevent two confirmed reservations for the same scarce design.

### Deposit
Deposit is tied to a specific request or flash reservation.

Payment implementation is not yet decided.

### Artist Home
Morning-screen candidate:
- books status
- new requests
- active flash holds
- deposits / reservation status

### Onboarding
Short structured questionnaire should generate the initial site rather than open a blank page builder.

Candidate inputs:
- name
- city
- styles
- price floor
- books status
- deposit amount
- policies
- portfolio / flash media

AI may assist with bounded draft copy such as bio, booking instructions, FAQs and SEO text.

## Success metrics

Issue #11 defines the operational metrics in detail.

Current measures are:

1. **Time to usable bio link** — setup start until a live page the artist is willing to publish/use; working target median under 10 minutes.
2. **Qualified-request decision readiness** — percentage of submitted requests assessable without first asking for missing required qualification information; initial validation target >=80%.
3. **Qualification back-and-forth** — median clarification messages after a structured request; initial validation target <=1.
4. **Flash reservation integrity** — zero double-confirmed reservations for one scarce flash design; hard invariant.
5. **Commercial conversion** — at least one real external client completes a qualified request or flash reservation through Tessnova during validation.
6. **Retained workflow use** — repeated real workflow activity after activation; no hard percentage is approved yet because retention confidence remains medium-low.

See `docs/product/tattoo-v1-icp-jtbd-success.md` for definitions, evidence boundaries and M3 tests.

## Explicit postponements

- public slot picker
- full calendar
- CRM
- newsletter
- form builder
- custom-domain support as universal P0
- multi-artist studio workspace
- marketplace / public artist directory
- freeform theme editor
- carts
- proposal system
- contract generation
- referral program
- generic vertical framework
- generic rules engine
- speaker/event product code

## Visual requirement

The experience must not feel generic, dull or obviously AI-generated.

Themes should eventually vary composition and layout—not merely color—while preserving structured Tattoo data.

Tesnova.com remains a craftsmanship / interaction-quality reference, not a source to copy.
