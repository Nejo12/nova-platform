# ADR-002 — Use Nova UI as the shared product design system

**Status:** Accepted

Tessnova will consume:
- `@nova-component/ui`
- `@nova-component/design-tokens`

Nova UI remains domain-agnostic.

A component starts in Tessnova if it is product-specific. It may be promoted to Nova UI only when its API and behavior are genuinely reusable across Nova products.

Do not add domain concepts such as `TattooFlashCard`, `WeddingPackage` or `SpeakerTopic` to Nova UI.
