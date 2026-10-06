# Tessnova / nova-platform

**Status:** M2 — Product Definition  
**Commercial brand:** Tessnova  
**Engineering repository:** `nova-platform`  
**Launch vertical:** Tattoo

Tessnova is a profession-specific professional-presence and client-acquisition product. The long-term architecture may support multiple verticals, but the first product is intentionally Tattoo-specific.

## Roadmap state

- M0 — Foundation: **complete**
- M1 — Market Validation: **complete**
- M2 — Product Definition: **active**
- M3 — Product Design: waiting
- M4 — Technical Architecture: waiting
- M5 — MVP Alpha: waiting
- M6 — Private Beta: waiting
- M7 — Paid Beta: waiting

## Launch decision

- **V1:** independent tattoo artists
- **Second-vertical stress test:** Wedding / Events
- **Later opportunity:** Professional Speakers

See `docs/decisions/ADR-004-tattoo-launch-vertical.md`.

## Nova ecosystem

Tessnova belongs to the Nova product family and consumes:

- `@nova-component/ui`
- `@nova-component/design-tokens`

Nova UI remains product/domain-agnostic. Tattoo-specific components, rules, themes and terminology stay inside Tessnova unless a later real consumer proves a genuinely reusable contract.

## Governing implementation rule

**Build one Tattoo product first. Extract shared platform contracts only after a second real vertical proves the reuse.**

The broader platform/capability diagrams are conceptual destination models, not instructions to create generic packages, schemas, a rules engine or a `vertical` column in V1.

## Current gate

Do **not** begin production implementation until M2 Product Definition is explicitly approved.

## Source of truth

- **GitHub:** requirements, roadmap, ADRs, research decisions and implementation status
- **Figma:** UX, visual design, flows, design foundations and prototypes
- **Claude Design:** divergent exploration only; not canonical
- **Nova UI:** reusable domain-agnostic UI primitives and semantic tokens
