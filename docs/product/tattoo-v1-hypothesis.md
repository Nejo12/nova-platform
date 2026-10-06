# Tattoo V1 — Product Hypothesis

**Status:** M2 working hypothesis — not yet approved V1 specification

## Target customer hypothesis

Independent tattoo artist or small-chair-renter who:

- gets a large share of discovery through Instagram;
- handles enquiries manually through DMs/email/WhatsApp;
- uses PayPal/bank transfer/payment links for deposits;
- manages books-open / closed communication manually;
- may sell or reserve flash;
- wants a distinctive professional presence, not a generic template.

Multi-artist studio management is out of scope for the first product definition.

## Core customer job

**Turn social attention into qualified tattoo work without losing serious enquiries, repeating the same questions, or double-selling scarce flash.**

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

## Candidate success metrics

1. **Time to usable bio link** — time from signup to a page the artist is willing to publish in their Instagram bio.
2. **Qualified request rate** — proportion of incoming requests containing the information required for the artist to assess suitability.
3. **Flash reservation integrity** — zero double-confirmed reservations for one flash design.
4. **Commercial conversion** — at least one real request / deposit through Tessnova during concierge or beta testing.

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
