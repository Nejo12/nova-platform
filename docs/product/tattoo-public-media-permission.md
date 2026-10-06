# Tattoo V1 — Public Media Publication Permission

**Status:** M2 Issue #28 — **PROPOSED for Founder approval; not a legal opinion**  
**Issue:** [#28 — Decide Tattoo portfolio-media publication permission](https://github.com/Nejo12/nova-platform/issues/28)  
**Prerequisite for:** [#17 — final Tattoo V1 definition / M2 approval](https://github.com/Nejo12/nova-platform/issues/17)  
**Scope:** Only public Tattoo portfolio and Flash media, and boundaries with private Custom Request references. No production architecture, legally binding copy, uploads, storage, consent-record schema, photo-moderation system or cross-vertical extraction.

## 1. Authority and rationale

**Existing approved Tattoo contract, preserved:**

- [#11: Tattoo ICP / activation](tattoo-v1-icp-jtbd-success.md): authentic, credible work on a live shareable link with an actionable Custom Request and/or Flash path is central to activation.
- [#12: Tattoo domain semantics](tattoo-domain-semantics.md): reference images supplied for Custom Requests are client qualification data, not portfolio; Flash is scarce inventory with its own states.
- [#13: storefront](tattoo-storefront-ia-themes.md): real artist work appears prominently; media storage/consent mechanics were explicitly deferred.
- [#14: deposit and reservation semantics](tattoo-deposit-semantics.md): financial/Flash states and artist ownership must remain independent from presentation.
- [#15: onboarding](tattoo-onboarding-ai-artist-home.md): at least one authentic **authorized** public image is the proposed publishability minimum; **affirmative publication-authority acknowledgement** is required for every publicly used portfolio/Flash asset; no automatic publication; a withdrawal must stop public display; client reference media never becomes public by default.
- [Operating system](../governance/project-operating-system.md), [M2 roadmap](../roadmap/M2-product-definition.md) and [AGENTS.md](../../AGENTS.md): explicit Tattoo publication-permission requirement; no private participant/client data in repo; product-specific first.

**Evidence distinction:** TAT-01/TAT-02 support real-work visual credibility, not a specific media-consent workflow. This document's gate design is a **risk-reduction product recommendation** under Issue #28, **not** a participant-validated consent preference. Approval is by the Founder through review/merge, and applicable law still needs professional review before an externally live implementation.

## 2. Legal context — primary sources, not a final legal determination

Sources checked on **6 October 2026**:

| Source | Narrow relevance | Do not infer |
| --- | --- | --- |
| [GDPR Art. 5–7](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng/) | Processing of personal data needs a lawful basis; where **GDPR consent** is the chosen basis, it must meet consent conditions and be withdrawable. | An artist ticking a Tessnova checkbox is **not** the pictured client's GDPR consent, and consent is not the only theoretically possible lawful basis. |
| [GDPR Art. 9](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng/) | Some identifiable images and context could reveal protected information; special-category processing needs separate legal analysis when applicable. | Every tattoo or close-up automatically is special-category data, or a platform can automatically determine this. |
| [GDPR Art. 17](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng/) | Erasure obligations may arise depending on the facts, legal basis and statutory exceptions. | Hiding an image from a web page necessarily fulfills every erasure or external-copy obligation. |
| [KunstUrhG § 22](https://www.gesetze-im-internet.de/kunsturhg/__22.html) and [§ 23](https://www.gesetze-im-internet.de/kunsturhg/__23.html) | German portrait/image-publication rules include a consent principle and legally limited exceptions. | A tattoo photo taken with a client's cooperation equals permission for later open-web marketing, or a § 23 exception applies without legal evaluation. |
| [UrhG § 19a](https://www.gesetze-im-internet.de/urhg/__19a.html) and [§ 72](https://www.gesetze-im-internet.de/urhg/__72.html) | Public online access and photographic rights are distinct from the tattoo artist's authorship of the tattoo design. | Creating the tattoo automatically grants copyright/publication rights to every photo of it or third-party artwork in a Flash graphic. |
| [EDPB consent guidelines 05/2020](https://www.edpb.europa.eu/documents/guideline/guidelines-052020-on-consent-under-regulation-2016679_en) | Official guidance helps interpret GDPR consent validity and withdrawal. | A default-checked form, blanket waiver or proofless assertion will always meet requirements. |

**Legal questions deferred to qualified review before actual launch:** Tessnova versus artist controller/processor roles, legal bases for actual site processing, enforceable rights/licence terms and notices, photo/identifiable-body/underage treatment, copyright/portrait law interplay, public-report and takedown obligations, complaint response targets, retention/erasure/backups/CDN/cache, cross-border issues and GDPR Article 9 triggers. Do not claim the recommended product gate itself makes publication lawful.

**Product caution:** “face not shown” does **not** always prove non-identifiability; a distinctive tattoo, setting or other context could allow recognition. Conversely, a wholly original Flash drawing depicting no real person may raise rights/licensing issues but not necessarily the same subject-privacy issues.

## 3. Founder approval proposal — the narrow V1 product rule

### Decision A — per-public-asset publication authority (recommended: REQUIRE)

Before **each** image/video intended for publicly visible Tattoo portfolio or Flash use can be published, the artist must make an **explicit, unchecked-by-default, affirmative acknowledgement** for that asset, confirming:

1. The artist **has the necessary rights or permission to use/publicly display the actual file on the Tessnova public storefront**, including any photographer/creator/licensor rights.
2. **If a real person is or may be identifiable**, the artist has confirmed that public commercial display is lawful under the applicable person's-image/privacy rules; where subject consent is the relied-on permission, it must cover the relevant public use. A tattoo-service appointment, photo-taking permission, DM exchange or prior Instagram post is **not** treated as proof of Tessnova publication authority.
3. The artist understands that they must keep that authority valid for the period of display, stop use and report/rescind an item when it is disputed or withdrawn, and can leave an uncertain item private.

This confirmation is **the artist's representation to Tessnova**, **not** first-hand consent from any depicted customer. The product must not call it “client consent obtained by Tessnova” or “verified rights.”

**V1 implementation intent (not schema):** confirmation applies to each specific intended public asset, including adding one later or changing its source. An explicit selection/review of multiple items can be designed in M3 only if each asset is clearly covered; do not replace this with a single buried account-level Terms checkbox, prechecked control or silent AI inference. Evidence of permission is **not** uploaded to Tessnova by default; the artist must be able to substantiate their own assertion if challenged, with legal/operational proof standards left for M4 review.

### Decision B — separate media categories and conservative risk boundary (recommended)

| Media in product | Publishability recommendation | Why |
| --- | --- | --- |
| **Original Flash drawing/design without a real depicted client** | Permit public use **after per-asset rights confirmation**, appropriate content check and #14 Flash readiness; no fictional client permission request is needed when no real person is identifiable. | An original design still may incorporate third-party copyright or publicity rights; do not assume all designs are safe by default. |
| **Photo of a completed tattoo, with a possibly identifiable real client** | Keep private until artist confirms **both** rights in the photograph/content **and** legal authority to display the person publicly, as applicable; otherwise unavailable for publication. | Creating the tattoo is not identical to owning photo rights or subject-publication permission. |
| **Tattoo close-up with no face visible** | Same two-part confirmation **if the client may be identifiable from tattoo or context**. An artist must be able to choose “not sure,” which blocks publication. | No-face does not categorically eliminate personal-data/portrait implications. |
| **Unclear owner, third-party image, stock/reference art, disputed subject or rights** | Keep private; no public portfolio/Flash rendering, no public Flash claim based on that media. | No implied licence/permission from possession, upload, repost or original DM. |
| **Images of a potentially identifiable minor, or sensitive/intimate exposure requiring special review** | **Conservative V1 recommendation: do not publish without separate specialist-approved policy**; keep private by default and defer any exception design. | Extra risk; this is a proposed product-risk limit, **not** a claim that all such photos are categorically unlawful. |
| **Client-provided Custom Request references, cover-up photos and private messages** | **Always private qualification materials in Tattoo V1.** No “promote to portfolio” one-click reuse. | #12/#15 already separate private request intake from public artist work. Later repurposing would require an independently designed rights/consent purpose and explicit authorization. |

**No automated biometric recognition, identity/age inference, model-generated permission, moral-content classifier or generalized consent engine** is authorized in M2.

### Decision C — publication and withdrawal behavior (recommended: FAIL CLOSED)

Use simple **publication eligibility**, not a new domain-level image lifecycle or public status enum.

```text
Private / draft media
  ↓ Artist chooses public portfolio or Flash use
Check source rights and (where applicable) person's-publication authority
  ├─ missing / uncertain / disputed / sensitive escalation → remain private
  └─ affirmative per-asset confirmation → eligible for artist preview
  ↓ Artist explicitly publishes / updates public storefront
Visible only while publication authorization remains valid
  ↓ Artist withdraws authority or receives credible dispute
Remove from publicly served page and disable new claim path depending on that media
  ↓ Artist resolves or replaces item
No automatic republication; re-confirm each asset before explicit update
```

1. **Upload ≠ publish:** a stored private draft may exist with no public access. An unapproved item must not appear publicly in previews that are accessible to outsiders, thumbnail metadata, social sharing cards or portfolio/Flash claims.
2. **Per-asset controls:** artist can **unpublish/remove from public use** any public asset; removal of one photo does not silently remove the artist's unrelated work or change Books.
3. **Complaint / withdrawal:** if the artist reports lost permission, or Tessnova receives a **credible rights/privacy complaint**, the affected media is promptly hidden from public serving while reviewed. A complaint is not deemed legally proven; the conservative restriction avoids continued disputed exposure. No automatic republication after a successful appeal without renewed artist review.
4. **Originals/variants:** removal from **public use** should include gallery view, Flash image, public thumbnails/preview variants, social-preview embeds and links under Tessnova control. Actual purge mechanics, CDN timing, indexing/search and backup retention/erasure **are M4/legal decisions**, not promised here. Distinguish unpublishing from full legal deletion.
5. **Last authorized portfolio asset removed:** #15 publication-readiness minimum is no longer met. Flag the page as **not publication-ready** in Artist Home; allow the artist to replace permitted media or intentionally unpublish the storefront. M3 must determine truthful existing-live fallback, avoiding exposure of the withdrawn asset or silent creation of new Custom/Flash promises. Do not count a broken page as newly activated.
6. **Flash-specific integrity:** hiding its media **does not** turn RESERVED/BOOKED into AVAILABLE, cancel a financial obligation, refund or re-release the design. A Flash item with no eligible public visual must stop offering **new** public claim attempts; existing hold/reservation/Deposit situations require artist-facing resolution under #12/#14, **not** an automatic inventory-state change. M4 will need a safe atomic enforcement strategy.
7. **New uploads / replacements:** permission is **not** inherited from a previous file, a template switch or an earlier tattoo appointment. A replacement requires its own confirmation and explicit publish/update action.
8. **Public links in the wild:** Tessnova can control only assets it serves and its own indexed URLs; no guarantee it can erase third-party screenshots, social reposts, browser caches or independent copies. Legal obligations regarding requests to recipients/search providers require separate review.

### Decision D — honest artist notice and recourse (recommended)

**Artist-facing content requirements, final wording awaits legal review and #29 locale decision:**

- Explain **why** the question is asked: the public link can be viewed and shared by anyone, not only followers or existing customers.
- Present the distinction between **rights to the file** and **permission/lawful basis concerning recognizable people**.
- Give an honest “I am not sure / keep private” escape path.
- State that the artist is responsible for supplying truthful authorization information; Tessnova's check is not independent verification.
- Make public removal accessible after publishing and provide a visible way to report/resolve disputed media via a narrowly scoped support route (not a CRM or case-management module).
- **Do not** claim a client's privacy rights are waived, that the platform has obtained their consent, or that all media is legally cleared.

**Illustrative UX copy for M3 exploration — not final legal text:**

> **Before publishing this image:** I confirm I have the rights needed to show this file on my public Tessnova page. If a person can be recognized, I also confirm I have the legal permission or other valid basis needed to display them publicly. If I'm not sure, I'll keep this image private.

Alternative in the same step: **Keep private**.

**Privacy/rights complaints:** people with a concern must have a usable contact/report path at launch; exact response process, reporting identity, controller responsibility, SLAs, evidence requests and deletion rights need M4/legal review. Avoid inventing a fully automated complaint workflow.

## 4. Publishability cases — no contradictions with #11–#15

| Scenario | Expected product behavior |
| --- | --- |
| Artist-created Flash design, all necessary rights confirmed, no actual person depicted | Media eligible; **public Flash claim** still additionally requires #12 available inventory, #14 positive deposit/currency and policy. |
| Real tattoo photo with identifiable client; valid use rights not confirmed | Keep private; no public display. |
| Close-up lacking face but with recognizable tattoo/client context | Treat as potentially identifiable; require artist's subject-publication authority confirmation. |
| Photographer shot finished work; artist received the file but not publication licence | Do not publish until necessary photo rights are confirmed. |
| Artist selects "not sure" | Save as private draft, show a clear follow-up task; never infer consent/permission. |
| Private Custom Request photo supplied by prospective client | Stays private to the request; not part of the public portfolio, even if the artist likes the design. |
| Artist initially published with permitted image, later receives withdrawal | Hide that asset from public delivery; surface readiness/alternative media task; **do not** retroactively mark historical first activation as never achieved. |
| Public Flash artwork permission is disputed during a hold | Hide artwork and stop new public claims; **do not automatically mutate** HOLD_PENDING_PAYMENT, RESERVED, BOOKED or Deposit. Existing commitments handled separately. |
| Artist removes final public portfolio image while Books OPEN | Stop serving withdrawn media; Artist Home flags below-minimum readiness. M3 defines safe existing-live representation; do not silently close/reopen Books. |
| Theme/crop/description/AI draft changes | Cannot override the authorization gate or turn private references public. |

## 5. P0 vs M3/M4 boundary for final #17

**Proposed Tattoo V1 P0 product capabilities (subject to Founder approval):**

1. Per-asset affirmative authority acknowledgement before **public** portfolio/Flash use.
2. Clear distinction between file-rights and identifiable-person-publication rights; uncertain assets stay private.
3. Public media not derived from private client references by default.
4. Artist-initiated removal and safe restriction of disputed assets from public display.
5. Media permission/readiness affects public portfolio/Flash eligibility without mutating Flash exclusivity, deposits or Books.
6. Access to a narrow rights/privacy report/contact route appropriate for launch (legal/operational design later).

**P1 / later candidate:** nice-to-have per-image permission helper guidance, clearer multi-asset review ergonomics, rights self-audit tooling, accessible media credit display when required/appropriate. No evidence yet warrants building these during M2.

**Explicitly not authorized:** collecting signed client release forms inside Tessnova, e-signatures, a consent CRM, automatic verification of client identity/legal consent, media-rights licensing marketplace, auto-reuse of private reference images, automatic image screening, generic asset-domain modules, or an Events-specific policy system.

**M3 Product Design:** artist comprehension test of two-part confirmation; correct placement in shortest onboarding and later image editing; confidence/uncertainty affordance; private/public preview distinction; negative states; warning copy; accessible keyboard/mobile behavior; report/remove controls; Flash image withdrawal with active reservation; closing Books does not affect public image permission; localized copy only after #29.

**M4 Architecture / operational/legal requirements (not choices made here):** role allocation and DPAs, actual legal bases and compliant notices/consent where applicable, minimally necessary recording of acknowledgement, authorization enforcement, safe private media storage and access, temporary/public URL control, generated derivatives and caches, takedown/complaint routing, backup/retention/erasure, signed release evidentiary standards where needed, copyright disputes, security of private client images and metadata (including EXIF/location), cross-region processing, migration, and tests for public/private leaks.

## 6. Risk, evidence and open Founder choices

| Question | Proposed #28 choice | Alternative / trade-off |
| --- | --- | --- |
| Single Terms checkbox or per-asset? | **Per-asset explicit acknowledgement** before public use. | Account-level only is quicker but weakly connects confirmation to an actual photograph/subject; harder to assess changed images. |
| Distinguish original designs and real-person photos? | **Yes**; photos require specific identifiable-person consideration. | A single rights sentence may hide a material privacy gap. |
| Proof of rights uploaded into Tessnova? | **No for V1 by default**; artist attests and retains supporting evidence independently. | Collecting proof might aid dispute response but adds especially sensitive data/privacy/storage/verification obligations; legal review may still require stronger launch controls. |
| Unknown permission? | **Fail closed** (draft, not public). | Publishing anyway exposes clients without verified authority. |
| Minors and high-risk intimate/sensitive media? | **Restrict V1 public publication by default pending qualified review.** | Permitting case-by-case requires a clear legally reviewed policy and moderation/support workflow not in M2 scope. |
| Withdrawal/dispute? | **Promptly restrict affected public media**, keep unrelated Tattoo financial and inventory states intact. | Waiting for complete legal adjudication may continue public exposure; instantly deleting all backing records could undermine retention/legal duties. |
| Whose legal consent does artist checkbox represent? | Only the **artist's own representation**, not the client's own consent. | Treating it as client GDPR consent would be misleading. |

These are **proposals**, not silently preapproved rules. Founder merger of the Issue #28 PR signifies approval of the product-rule choices only; it does **not** constitute external legal counsel's clearance or deployment authority.

## 7. Founder approval checklist — #28 only

- [ ] Require per-public-asset, unchecked affirmative confirmation covering file rights and subject-publication authorization where applicable.
- [ ] Differentiate original Flash artwork from client photos; do **not** treat face absence, tattoo creation, social posting or photo capture as automatic permission.
- [ ] Exclude unclear/disputed or especially sensitive/minor media from V1 public display without specialist-approved exception.
- [ ] Keep client-submitted Custom Request references private and independent of artist public portfolio/Flash.
- [ ] Artist can withdraw an image; credible complaints trigger prompt restriction; actual erasure and legal routing remain separate M4 decisions.
- [ ] Existing Flash holds, RESERVED/BOOKED states and Deposits never auto-reset because of media withdrawal.
- [ ] Maintain #15 one-authorized-work-image publishability/activation meaning; flag lost readiness honestly.
- [ ] No schema, auth, provider, consent-record system or external operational/legal claims made in M2.
- [ ] #29 initial locale and #17 final P0/P1/non-goals gates remain OPEN.
- [ ] Obtain appropriate independent legal review before the public launch, including data-controller roles, photo/person permission, copyright and downstream erasure.

**Approval scope: Issue #28 Tattoo public-media product contract only.** No Events extraction, M2 closure or production implementation. Founder performs all merges manually.
