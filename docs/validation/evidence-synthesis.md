# M1 Evidence Synthesis

**Round:** 1  
**Participants:** TAT-01, EVT-01, SPK-01  
**Status:** Sufficient for directional vertical selection; not statistical market proof.

## High-confidence cross-vertical findings

### 1. The public page is not the product by itself

All three professionals described value in **qualification and workflow**, not generic site-building.

- Tattoo: avoid weak DMs and unsafe flash reservation.
- Events: qualify date/venue/guest-count/budget before proposal effort.
- Speakers: centralize current assets and collect event constraints before email back-and-forth.

### 2. Generic presentation is actively rejected

- Tattoo rejects a page that looks like every other artist.
- Event professional explicitly rejects dull/generic/AI-look software.
- Speaker accepts a shared template, but still needs a personal-domain-quality professional presence.

Tessnova must combine strong defaults with vertical-specific visual credibility.

### 3. “Availability” is three different domain concepts

| Vertical | Actual concept |
|---|---|
| Tattoo | Books status; guest-spot note |
| Events | Event date + venue + operational collision |
| Speakers | Event constraints: date, city, travel, audience |

Do not build a generic availability module from these three nouns.

### 4. Public pricing rules differ materially

| Vertical | Pricing preference |
|---|---|
| Tattoo | Minimum/public floor useful |
| Events | Starting floor useful; full pricing private |
| Speakers | Fee should remain private |

This is evidence for vertical rules rather than a generic price-table capability.

### 5. Payments have different roles

- Tattoo: deposit is tightly coupled to flash/request state and can prevent double-selling.
- Events: deposit is part of booking/proposal/contract workflow; 50% is normal in the participant's process.
- Speakers: invoice is the commercial mechanism; website payment is not core.

### 6. No participant asked for a public slot picker

Scheduling/calendaring should not be assumed to be V1.

## Evidence table

| Evidence | Vertical | Severity | Existing workaround | Tessnova implication | Confidence |
|---|---|---:|---|---|---|
| Two people paid for same flash before claimed state updated | Tattoo | 5 | Instagram caption + PayPal | Flash hold/reservation state must be atomic | Strong |
| Weak DMs require multiple messages before suitability known | Tattoo | 4 | Manual DM/email qualification | Fixed custom-request flow | Strong |
| Books status and waitlist get stale/lost | Tattoo | 4 | Bio + Stories + saved DMs | Books state + optional later waitlist | Strong |
| Budget mismatch wastes florist enquiry effort | Events | 4 | PDF sent after manual qualification | Date/venue/guest/budget qualification | Strong |
| Slow response after event weekends loses leads | Events | 4 | Email/manual quote | Faster structured intake + follow-up | Medium-strong |
| Speaker assets live across site/PDF/Drive and go stale | Speakers | 3 | Manual email attachments/links | Current one-pager + asset hub | Strong |
| Event constraints arrive late for speaker | Speakers | 3 | Multi-email back-and-forth | Fixed event-enquiry flow | Strong |

## Jobs-to-be-done

### Tattoo
When someone finds my work online, I want them to understand whether I am booking, send a usable request, or safely reserve flash with a deposit, so I do not spend my time qualifying bad DMs or accidentally sell the same design twice.

### Events
When a couple wants to contact me, I want them to provide the date, venue, guest count and realistic budget before I prepare material or a proposal, so I spend time only on viable weddings.

### Speakers
When an organizer evaluates me, I want one current place for talks, reel, bios, photos and event constraints, so I do not repeatedly send stale assets across multiple emails.

## Provisional vertical recommendation

**Tattoo first. Events second stress-test. Speakers later.**

Tattoo has the strongest distinctive stateful loop:
**bio link → books/work/flash → qualified request or flash hold → deposit → artist dashboard.**

That loop creates recurring operational value and switching cost beyond a static site.

## What this evidence does NOT prove

- total addressable market size;
- broad willingness to pay across the vertical;
- exact pricing;
- final payment architecture;
- final theme preferences;
- whether Stripe Connect is acceptable;
- retention over time.

These should be tested in M2/M3 prototype and concierge validation rather than requiring 20 interviews before progress.
