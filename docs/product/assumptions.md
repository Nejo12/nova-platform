# Assumption Register

| Assumption | Current state | Validation / next test |
|---|---|---|
| Profession-specific products outperform generic builder positioning | Strongly supported | Six workflow interviews + competitive/product analysis |
| Tattoo is the strongest first launch vertical | **Accepted M1 decision** | ADR-004; TAT-01/TAT-02 |
| One shared platform can serve several verticals without degrading UX | **Still unproven; #16 paper stress-test does not establish shared domain contracts** | [Events florist comparison](events-florist-paper-stress-test.md): existing Nova UI generic primitives can be reused; Books/Flash/Custom Request/Deposit semantics do not transfer unchanged. Revisit extraction only after a second real vertical proves the same five contract dimensions |
| Independent, social-led artists with recurring manual qualification pain are the strongest Tattoo V1 ICP | Medium-high | Issue #11 synthesis of TAT-01/TAT-02; challenge with M3 prototype participants |
| Structured onboarding is preferred to a blank editor | Medium-high hypothesis | M3 prototype test |
| A credible publishable Tattoo page can be configured in under ~10 minutes | Unproven / medium | M3 timed onboarding/prototype test |
| One-page public presence is sufficient for Tattoo V1 acquisition surface | Medium-high | TAT-01/TAT-02; validate prototype |
| Qualification/workflow value exceeds page customization value | Strongly supported | TAT-01/TAT-02 and cross-vertical research |
| Structured requests materially reduce qualification back-and-forth | Medium-high hypothesis | M3 task testing; later concierge/beta measure decision-ready rate and clarification messages |
| Ongoing request/Books/Flash/reservation workflow creates retention beyond a static bio page | Medium-low | M3 concept validation; later observe repeated real workflow use after activation |
| €19/month is a plausible initial Tattoo test price | Medium | TAT-01 explicit yes at €19; TAT-02 decision point around €20 |
| Integrated deposits increase Tattoo willingness to pay | Medium | TAT-01 supports higher price with deposit collection; both use deposits today |
| A fixed 15-minute Flash hold is enough time to pay without locking scarce inventory too long | Unproven / medium | Issue #14 product hypothesis; test in M3 Flash-reservation prototype |
| Separate artist-level Custom and Flash deposit defaults are sufficient without per-request amount overrides | Medium | TAT-01 uses different fixed Custom/Flash amounts; test flexibility need in M3 |
| V1 Deposit should always be credited toward final tattoo price | Medium | Directly supported by TAT-01; no contradictory evidence from TAT-02; validate in M3 |
| Custom domain is a universal Tattoo P0 requirement | **Not supported** | TAT-02 cares; evidence is mixed; keep out of universal P0 pending prototype tests |
| Public calendar / slot picker is required | **Rejected for V1** | Tattoo and Events evidence favors requests/manual confirmation |
| Generic visual templates are acceptable | **Rejected** | Tattoo + Events participants explicitly reject generic/template/AI-looking presentation |
| Curated themes can create enough artist individuality without a freeform page builder | Medium | Issue #13 product hypothesis; test materially different M3 compositions with tattoo artists |
| One representative authorized work image can satisfy the minimum publishable portfolio gate without degrading perceived credibility | Unproven / #15 hypothesis | M3 timed onboarding plus artist/visitor credibility assessment; adjust minimum only with explicit Founder decision |
| A draft Books CLOSED default with explicit confirmation prevents accidental intake without hurting activation | Unproven / #15 hypothesis | M3 compare safe CLOSED default vs explicit choice; observe accidental OPEN and setup comprehension |
| Books CLOSED without actionable Flash can still serve as an honest informational public page without counting toward activation | Proposed #15 distinction; value unproven | M3 test artist intent and visitor next-action clarity; keep Issue #11 conversion-path activation definition intact |
| Conditional Flash amount/currency/policy and media gates will prevent unsafe reservation publication without slowing Custom-only activation | Unproven / #15 hypothesis | M3 task-based onboarding tests with Flash/non-Flash artists; verify no unready Flash claim is exposed |
| A focused Books/requests/Flash-hold/deposit Artist Home lets artists spot meaningful work without a CRM | Unproven / #15 hypothesis | M3 scenario-based discovery and state-comprehension tests, including late payments and accepted-but-not-booked work |
| Optional human-reviewed AI drafting improves setup quality or speed without fabrication | Unproven / #15 hypothesis | M3 measure skip/use/edit time and factual/policy errors against manual copy workflow |
