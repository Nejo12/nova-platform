# Tattoo V1 — Initial Language and Locale Contract

**Status:** M2 Issue #29 — **PROPOSED for Founder approval**  
**Issue:** [#29 — Decide initial Tattoo V1 locale and public language](https://github.com/Nejo12/nova-platform/issues/29)  
**Prerequisite for:** [#17 — final Tattoo V1 specification and M2 gate](https://github.com/Nejo12/nova-platform/issues/17)  
**Scope:** Product-facing language support, artist-authored content, client comprehension, regional formatting and P0/P1 boundaries. **Not** an i18n implementation, translation package, production locale strategy or legal-language ruling.

## 1. Decision summary — review before Founder merge

**Recommended bounded Tattoo launch choice (not yet approved):**

1. **P0 interface language: German** for the **artist-facing onboarding and Artist Home**, **public storefront system labels**, **Custom Request submission and client confirmations**, **Flash reservation/Deposit system disclosures**, and any system-generated warnings and support/privacy routes.
2. **Launch language tag: `de`; regional formatting context: `de-DE`** where needed for Germany-oriented prices, dates and numbers. These are product expectations, not database or framework configuration.
3. **No P0 language selector, automatic translation or alternate-language system UI.** The UI must never silently mix unrelated German/English system copy or claim to support English if key action/payment screens remain German.
4. **Artist-authored content may be in another language**, such as English, and must not be silently translated or rewritten. A page with English artist biography is **not** an English-language version of the German client workflow.
5. **Deposit-enabled paths require client-comprehensible, artist-approved policy wording in the supported German UI.** If the applicable cancellation/refund policy is present only in another language, the artist must provide and approve an understandable German version **before accepting that payment path**. This is a proposed product gate, not a claim that a particular language is always legally mandated. An unready Flash deposit path stays unpublished; a Custom-only page may continue without payment.
6. **P1: evaluate English `en` interface support** for both artist and public/client flows as a coherent package, using M3/early-cohort evidence. Do not commit to a date, automatic migration, or partial “English supported” badges now.
7. **P0 contains no country restriction or forced language for expressive portfolio text.** Germany-oriented is a **launch hypothesis**, not proof of participants' language preferences, citizenship, or location-specific usage rights.

**Founder merge decision:** accept the proposed **single German supported interface language** for the initial Tattoo release and the honest mixed-content boundaries, **or revise this issue before approval** if bilingual-at-launch or English-first better matches the desired launch cohort. #17 must import the actual Founder-approved choice, not treat this hypothesis as inevitable.

## 2. Evidence vs inference

### Direct first-party research

- [TAT-01](../validation/interviews/TAT-01.md) is a Berlin-based independent fine-line tattoo artist. The interview discusses Books, qualifying references and size, artist-controlled deposit policy and Instagram-led demand.
- [TAT-02](../validation/interviews/TAT-02.md) is a Leipzig-based independent fine-line/botanical artist. The interview likewise discusses social enquiries, qualification and Flash double-booking.
- [M1 evidence synthesis](../validation/evidence-synthesis.md) supports the Tattoo launch vertical and the product need. **Neither interview records a preferred platform language, a multilingual requirement, or a formal willingness to use a German-only UI.**
- The domain `tessnova.de`, Germany-oriented discovery interviews and the approved Tattoo-first market focus make a German-language baseline **plausible**, but they are **not** an observed language preference or market-size study.

### Inference / product recommendation, not a research finding

A **single complete German experience** is proposed because the early discovered market context is in Germany and it keeps the mandatory request, deposit, policy, accessibility and support copy narrow and internally consistent. The alternative cost is excluding artists/clients unable or unwilling to operate those flows in German. This trade-off **must be explicitly accepted** rather than disguised as research.

The **second-language threshold is not measured**. Choosing German P0 does **not** reject eventual bilingual support; conversely, writing user free text in English is not evidence that a complete English client flow exists.

### Related approved product boundaries

- [#11 activation metrics](tattoo-v1-icp-jtbd-success.md) still require a credible live link with a functioning Custom Request and/or Flash action. A visible public page alone is not activation.
- [#12 Books / Flash / Custom Request states](tattoo-domain-semantics.md) and [glossary](tattoo-domain-glossary.md) retain exact meaning. This decision does **not** translate product states into appointment promises.
- [#13 public storefront](tattoo-storefront-ia-themes.md) still prioritizes identity, work, Books status, correct CTA and honest Flash state.
- [#14 Deposit semantics](tattoo-deposit-semantics.md): currency is explicitly displayed; Flash hold stays a fixed 15 minutes; a paid Flash reservation is **not** automatically an appointment; refund policy remains the artist's.
- [#15 onboarding/Artist Home](tattoo-onboarding-ai-artist-home.md): explicit publication after artist review; AI drafts optional and never overwrite real product truth.
- [#28 public media permission](tattoo-public-media-permission.md): no public image without per-asset authority; the product declaration is **not** the pictured client's consent. Final privacy/policy copy needs separate legal review and must be intelligible in the actual supported UI.
- [M2 roadmap](../roadmap/M2-product-definition.md) keeps language choice in Product Definition and technical implementation in M4. Events [#16 paper test](events-florist-paper-stress-test.md) authorizes **no** generic cross-vertical locale engine.

## 3. Alternatives evaluated — neither assumed approved

| Approach | Artist UI | Public storefront / client flow | Benefits | Risks / cost | #29 recommendation |
| --- | --- | --- | --- | --- | --- |
| **A. German-only initial product** | Complete German | Complete German for system actions and payment | One internally coherent testable language; realistic narrow scope for initial Germany-oriented Tattoo cohort | Some international artists/clients will be excluded; bilingual authored copy is not a substitute | **Recommend P0**, with explicit Founder acceptance of exclusion trade-off and M3 test |
| **B. German + English from first release** | Complete both languages | Complete both, including requests, payments, errors, support/privacy copy | Broader addressability for international artists and visitors; artist/client preference can differ | Twice the system copy/prototype QA; policy and privacy translation responsibility; state/CTA consistency risks | Viable **alternative if Founder prioritizes bilingual launch**; no direct interview evidence resolves trade-off |
| **C. English-only initial product** | Complete English | Complete English | Narrow copy/QA surface; potentially suits some international artists | No participant preference evidence; German-based clients may be excluded despite Germany context | Not recommended absent a specific English-first cohort decision |
| **D. Split artist/public default languages** | One language | Another language | Could fit a specific discovered artist/client pair | High misunderstanding risk in policy, accepted requests and deposit flow; more testing than one coherent language | **Do not choose by default**; needs evidence |
| **E. “Free-text English means bilingual platform”** | Mixed/incomplete | Mixed/incomplete | Low initial effort | Misrepresents supported actions; particularly dangerous in Deposit/Flash and privacy language | **Reject** as a supported-locale claim |

**Alternative B is a strategic Founder choice, not inherently forbidden.** This memo uses option A as the proposed M2 product contract. If the Founder chooses B or C, update the concrete language contract **in the same reviewed issue** before merging; do not leave inconsistent P0 declarations.

## 4. Surface-by-surface minimum contract

| Surface | Proposed P0 language | Content ownership / rule |
| --- | --- | --- |
| Signup / Tattoo onboarding / publication checks | German | System instructions and all mandatory media-permission explanations are coherent; artist explicitly confirms Books and public readiness. |
| Artist Home | German | Books, requests, Flash holds, Deposit status/errors and action buttons stay comprehensible without interpreting English internal enum names. |
| Public storefront controls | German | Navigation, state badges, CTAs, info/error/help text are German. **Artist-written name, bio, captions, style descriptions and process prose may differ.** |
| New Custom Request | German | Placement, size, colour, reference, cover-up, timing and contact fields; validation, success/failure and clarification messages remain German; user-entered text may be any language. |
| Books status | German explanation | **OPEN** means accepting new Custom Requests; **CLOSED** means not accepting new Custom Requests. No public appointment slot calendar or waitlist is implied. |
| Flash hold / confirmation | German | AVAILABLE / HOLD_PENDING_PAYMENT / RESERVED / BOOKED displayed with truthful plain-language distinction. Fifteen-minute exclusive hold is described accurately; RESERVED is not BOOKED. |
| Deposit amount and policy | German system text plus artist-approved understandable German policy | Artist sets the amount/currency and policy; no invented rules, automatic policy translation or misleading “paid Tessnova” wording. |
| Media-permission and privacy guidance | German system text, with legally reviewed final wording before launch | Per-asset artist acknowledgement in #28; do not mislabel it as direct client consent. Report/takedown route is understandable. |
| Optional AI drafting | Only if separately retained by #17 | Artist-authored source and human approval remain necessary; do not introduce a free translation feature or promise faithful legal translation. |
| SEO / social previews | German system labels; artist-provided text may vary | Do not advertise a translated destination that does not exist; supported audience-language metadata must match real page UI/content. |
| Support / transactional notices | German for P0 flows | If a workflow requires a customer-facing notice to be safe/usable, do not launch the flow with untranslated English-only instructions. Delivery transport is M4. |

**No automatic per-client language detection / personalization at P0.** Artist-authored foreign-language text is allowed, but the core public UI remains German and must not change based on a visitor's IP address, Accept-Language or social origin. System language and author's text are different contracts.

## 5. Content language, policies and truthfulness

1. **Artist owns authored content.** Tessnova must preserve original-language artist bios, portfolio captions, authentic credits and authored policy text, subject to #28 public-rights and agreed safety/legal controls. Platform must not silently edit tone or translate terms.
2. **System text is Tessnova-owned.** UI labels, request descriptions, Flash/payment guarantees, validation errors, platform privacy notices and publication-authority copy must be authored/verified for the supported language. Domain semantics must survive localization.
3. **Mandatory artist policy on an enabled payment path:** the artist must supply an understandable German version of their applicable cancellation/refund policy and approve what the client will see. The deposit cannot be paid on a path whose actual governing terms are inaccessible or contradicted by system messaging. This **does not** pick the refund policy, force a default or turn the platform into a translation/legal service.
4. **Optional non-financial biography/context text:** may be written in another language. It is not a promise that the resulting page is translated; show no “English available” platform badge.
5. **One language per coherent action:** public navigation, form instructions, error recovery, receipt/reservation clarity, and system policy disclosures must not switch unpredictably between languages. Tattoo vocabulary such as “Books” and “Flash” may be retained as industry jargon **when accompanied by comprehensible German explanations**.
6. **Manual bilingual authoring:** an artist may choose to include German and English text in their bio, but this is their own writing and not two functioning localized variants. No auto-generated mirror pages or indexed alternate-language routes at P0.
7. **Permissions / legal language:** #28 is a product acknowledgement, not proof of external client consent; approved platform/legal wording needs proper legal review in German before launch. Do not fabricate translated client permission statements.

### Illustrative M3 wording — NOT final UI/localization or legal copy

| Product meaning | Safe German wording candidate | Avoid |
| --- | --- | --- |
| Books OPEN | “Ich nehme neue Anfragen für individuelle Tattoos an.” | “Freie Termine jetzt buchen.” |
| Books CLOSED | “Derzeit keine neuen Anfragen für individuelle Tattoos.” | “Keine Flash-Designs verfügbar” solely because Books is closed. |
| New Custom Request CTA | “Tattoo-Idee anfragen” / “Anfrage senden” | “Termin verbindlich buchen” on a lead form. |
| Flash AVAILABLE | “Flash-Design verfügbar” | “Sofort bestätigt” before a paid reservation. |
| Flash temporary hold | “Dieses Design ist 15 Minuten für dich reserviert, während du die Anzahlung abschließt.” | An unrestricted guaranteed tattoo appointment. |
| Flash RESERVED, not BOOKED | “Design für dich reserviert; Termin noch nicht vereinbart.” | “Dein Tattootermin ist gebucht.” |
| Deposit | “Anzahlung auf den späteren Gesamtpreis” where applicable | Claiming payment completes an appointment or goes to Tessnova instead of the artist. |
| Public image right | “Ich bestätige, dass ich dieses Bild öffentlich zeigen darf.” **plus explanation of rights and recognizable people** | “Der Kunde hat Tessnova seine Einwilligung gegeben.” |

M3 must validate terminology with German-speaking independent artists and clients; the precise German vocabulary above is **illustrative**, not an approved final strings catalog.

## 6. Locale-sensitive display semantics

Language selection, display formatting, business currency and Tattoo domain measurements are **separate** choices.

| Item | Proposed P0 expectation | Explicit non-decision |
| --- | --- | --- |
| Text language | Page and controls are in German; where a technical language identifier is needed, use standard **`de`** for the content, potentially `de-DE` as a page-specific regional variant. | No i18n framework / language detection provider selected. |
| Regional number format | Germany-conventional human-readable grouping and decimal formatting; display must be unambiguous in amounts and size inputs. | No requirement to store monetary values or lengths as localized strings. |
| Currency | **Always show actual artist-configured currency with Deposit amount.** An example such as `80,00 €` is illustrative **only**. Changing language/number format does not change the underlying amount, currency or exchange rate. | **No** blanket assumption all payments use EUR; #14 owns positive Flash Deposit and artist amount/currency, M4 owns supported payment currencies and conversion restrictions. |
| Size | Tattoo Custom Request collects approximate dimensions **in centimetres (`cm`)** as #12 approved; clarify decimals and units in UI. | No auto-conversion to inches or locale-derived size units. |
| Dates / desired timing | Human-readable German month/window, without treating rough desired timing as a public appointment slot. Optional reopening notes remain informational; artist explicitly opens Books. | No public calendar, automatic Books reopening, date-slot search or appointment promise. |
| Flash 15-minute hold | Duration expressed clearly in German, a fixed elapsed-time product rule, not a date-localization setting. | No adjustable hold duration, calendar-based availability or invented time zone choice. |
| Names/locations | Preserve artist-provided proper names, styles and local terms faithfully. | No forced renaming of an artist identity for German SEO. |

**Accessibility / document-language requirement:** The rendered page must expose its **actual default language** and distinguish identifiable spans of other languages where applicable so screen readers can pronounce them appropriately. W3C [WCAG 2.2 SC 3.1.1 and 3.1.2](https://www.w3.org/TR/WCAG22/) and [language declarations / BCP 47](https://www.w3.org/International/questions/qa-html-language-declarations) define relevant standards. Technical implementation and how artist-authored mixed language is labelled belong to M4/M3; the product must not misrepresent a German UI as a localized English site.

**Formatting reference (not a prescribed library):** Unicode CLDR's [number and currency patterns](https://cldr.unicode.org/translation/number-currency-formats/number-and-currency-patterns) distinguish a locale's display pattern from the actual currency value/code.

## 7. Failure cases and guardrails

| Situation | Required safe product behavior |
| --- | --- |
| Browser prefers English but only German is supported | Display coherent German system UI; do not silently fall back to a partial English form or label. |
| Artist writes an English bio and German Books status | Preserve English artist text; German system labels and form still function; no English-flow claim. |
| A client enters an English Custom Request idea | Preserve customer text exactly; do not change whether required #12 fields are complete. |
| Artist provides only an English cancellation policy for German Flash deposit flow | Flash claim/payment stays **not ready** until artist provides/approves an understandable German version; Custom-only publication remains possible. |
| Long technical term “Books” looks English | Show a plain-language German explanation of accepting/not accepting custom requests; no “free appointments” implication. |
| A German date string is mistaken for an appointment | Wording must identify rough timing or optional informational Books-reopening note, not an actual reserved slot. |
| Artist writes Deposit as `80 EUR`; public format shows euro sign | Value and currency must remain the artist-set amount/currency; never silently convert or infer a different amount. |
| Artist changes storefront theme | Layout may change, but required language/action/state semantics cannot be hidden or translated into a false promise. |
| A public image is removed after permission withdrawal | #28's visibility and Flash-state separation holds independently of German/English text; no automatic Flash release or client-data publication. |
| Artist requests English UI mid-onboarding | Provide an honest explanation of currently supported interface languages; do not advertise an unfinished translated workflow or block preservation of a saved draft. |
| Flash hold expires during a locale/display change | The 15-minute real hold and #14 late-payment protection are unchanged. |

## 8. Proposed #17 scope classification

| Category | Items |
| --- | --- |
| **P0 — proposed** | Coherent German artist interface; coherent German public/client transaction flow; clear Tattoo-domain German copy; human-approved German Deposit/policy disclosures before payment; correct configured currency; cm and unambiguous date/window formats; correct page-language accessibility; honest free-text language separation. |
| **P1 — candidate, evidence gated** | Full English `en` artist + public/client interface together, including errors, Flash, Deposit, permissions, policies, notifications, help and accessibility; research on client/artists language switching. |
| **Postponed / not in initial V1** | Additional locales beyond explicit later approval; AI/machine translation of professional claims or legal terms; generic localization marketplace; automatic per-client detected translations; site-wide freeform multilingual versions; multi-vertical translation engine. |
| **M3 tests** | German-speaking artist onboarding comprehension; mixed German UI + English portfolio bio; an English-preferring client trying a German request/deposit flow; international artist fit; Books / Flash / Deposit vocabulary; screen-reader mixed-language reading; abandonment/safety signals. |
| **M4 decisions** | Translation resource management, web language metadata and mixed-language attribution, locale formatting/accessibility tests, storage versus formatted display, supported payment currencies, client notices, legal-review process and any later migration from one to two languages. No framework/package selected by this issue. |

**Evidence-triggered change rule:** If M3 testing exposes significant English-only client exclusion or unworkable safety/comprehension, **raise the conflict to the Founder** and revise P0 through a new explicit decision before launching; do not quietly add incomplete bilingual UX or override the approved initial scope.

**No changes** to the separate #28 media-permission rule, Tattoo #11–#15 meaning, Events #16 finding or #17's explicit approval gate.

## 9. Founder checklist for approval of #29 only

- [ ] Approve **German `de` system/UI language at Tattoo V1 initial release** for both artists and public clients, with regional `de-DE` display conventions where needed.
- [ ] Accept that **English is not initially a supported system UI**; it is a **P1, evidence-gated candidate**, not guaranteed future functionality on an announced date.
- [ ] Preserve artist/customer-authored free text in their original language, without claiming a translated client workflow exists.
- [ ] Require German-readable artist-owned policy for a P0 Deposit-enabled payment path; do not fabricate refund terms or automatically translate them.
- [ ] Preserve exact Books/Flash/Custom Request/Deposit meanings through clear German copy; no appointment implication.
- [ ] Display the actual configured currency; sizes remain centimetres; desired timing and reopening notes remain non-appointment text.
- [ ] Meet language-of-page/parts accessibility intent without choosing an i18n stack in M2.
- [ ] Keep #28 permission and privacy obligations intact, including future specialist legal review.
- [ ] No production implementation, cross-vertical locale engine, locale schema, provider choice or M3 Figma edits under #29.
- [ ] Proceed to #17 P0/P1/postponed **only after Founder merges the final chosen language contract**.

**Founder approval scope:** only Tattoo V1 language/locale product definition. This does not approve production architecture, start M3, or close M2; the Founder manually merges all PRs.
