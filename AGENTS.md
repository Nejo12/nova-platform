# Tessnova — Agent Instructions

These instructions apply to every AI agent and contributor working in `Nejo12/nova-platform`.

## Purpose

Tessnova is a profession-specific professional-presence and client-acquisition product.

The approved first launch vertical is **independent tattoo artists**. Wedding / Events is the second-vertical stress test. Professional Speakers is a later opportunity.

The long-term product may grow into shared platform infrastructure, but V1 must remain Tattoo-specific until real reuse proves otherwise.

## Authority and source precedence

Before making claims or changes, inspect **live GitHub state**.

Authority order:

1. current GitHub `main` and Founder-approved decisions;
2. accepted ADRs and current roadmap/product documents;
3. approved/canonical Figma for UX, visual and interaction behavior;
4. linked GitHub issue and its explicit acceptance scope;
5. implementation plan / PR;
6. tests and code as executable evidence;
7. handoffs, summaries, chat memory and external advice.

If higher-order sources conflict, **stop and surface the conflict**. Do not guess, silently reconcile, or invent a new decision.

Live `main` outranks stale handoffs and local notes.

## Founder-controlled workflow

The Founder performs **ALL merges manually**.

Never:
- merge a PR;
- auto-merge;
- enable auto-merge;
- push directly to `main`;
- infer Founder approval from a previous task or nearby conversation.

Normal substantial-change workflow:

1. inspect live `main`, relevant issue and authoritative docs;
2. identify unresolved product/design/architecture decisions;
3. obtain explicit Founder approval when a material decision is required;
4. create/use one bounded branch or isolated worktree;
5. implement only the approved scope;
6. run focused verification first;
7. run repository-required final verification once the change is stable;
8. review the diff for scope drift;
9. push branch and open PR when authorized;
10. verify exact-head PR state / CI;
11. stop before merge and give the Founder the merge gate;
12. after the Founder reports a merge, verify live new `main`, linked issue state and any required post-merge checks.

## Current phase gate

At the time these rules were established:

- M0 — Foundation: complete
- M1 — Market Validation: complete
- M2 — Product Definition: active
- M3+ — not yet active

**No production implementation begins until M2 is explicitly approved through the M2 closure gate.**

Current M2 work is tracked in Issues #11–#17. Always verify the live roadmap before acting.

Do not select:
- production framework;
- production database schema;
- payment-provider architecture;
- authentication architecture;
- deployment architecture;

during M2 unless a product-definition decision genuinely requires it.

## Accepted product decisions

These are not open brainstorming topics unless new material evidence appears:

- Brand: **Tessnova**
- Engineering repository: `nova-platform`
- Domain secured: `tessnova.de`
- V1 vertical: **Tattoo**
- second-vertical stress test: **Wedding / Events**
- later opportunity: **Professional Speakers**
- Nova UI is the shared domain-agnostic design-system dependency.
- Tessnova is separate from Klinnova and Slotnova.
- Tesnova.com is a permanent M3 design-quality reference, not a source to copy.

## Tattoo V1 discipline

Use Tattoo language and Tattoo rules first.

Working M2 concepts include:

- **Books** — booking-status/shop-sign concept; not a public slot calendar.
- **Flash** — scarce design inventory with reservation integrity.
- **Custom Request** — a lead/request; acceptance is not automatically an appointment.
- **Deposit** — attached to a specific flash reservation or request.

Hard product invariant to preserve:

> One scarce flash design must never have two confirmed customers.

These are M2 product semantics until finalized; do not prematurely convert them into a production schema.

## Architecture rules

**Product-specific first. Shared only when proven generic.**

Do not create speculative abstractions because a future vertical might need them.

Do not create without proven repeated need:
- generic capability packages;
- generic `vertical` schema/column;
- generic rules engine / workflow DSL;
- generic availability or booking module;
- workspace/org hierarchy for a solo-artist problem;
- `common`, `shared`, `core`, `utils` dumping-ground packages;
- universal base service/repository/entity abstractions.

A concept is eligible for extraction only when a second real use case shares substantially the same:
1. data shape;
2. invariants;
3. lifecycle/state semantics;
4. rendering/interaction needs;
5. ownership/security model.

Wedding / Events is a paper stress test before any shared extraction.

## Nova product boundaries

### Nova UI

Repository: `Nejo12/nova-ui`

Authoritative published packages:
- `@nova-component/ui`
- `@nova-component/design-tokens`

Nova UI owns generic primitives/tokens/accessibility behavior.

Tessnova owns:
- Tattoo storefront composition;
- Tattoo themes;
- Books status;
- Flash UI/flows;
- Tattoo request UX;
- Tattoo reservation/deposit product behavior.

Never add Tattoo-specific concepts to Nova UI merely for convenience.

### Klinnova / Slotnova

Do not modify Klinnova or Slotnova unless the exact task explicitly requires a bounded cross-repository change.

Tattoo functionality belongs in Tessnova, not Slotnova.

## Design authority

Canonical Figma:
**Tessnova — Product & Brand**

File key:
`OQmqaRuqB7qE5X3LTJsq7J`

Figma is authoritative for approved UX, visual design, interactions and prototypes.

Claude Design or other generative design tools are exploration tools only.

For material UI work:
- inspect approved Figma first;
- preserve Nova UI boundaries;
- verify keyboard/focus/touch behavior;
- preserve reduced-motion support;
- do not substitute generic AI aesthetics for approved product design.

Permanent design-quality reference:
`https://www.tesnova.com/`

Principle:
**Borrow the standard of craft, not the visual identity.**

Do not copy its code, assets, copy, layouts or branding.

## Research and evidence discipline

Keep **evidence**, **inference** and **hypothesis** separate.

Do not turn one participant request into a requirement.

Current research uses anonymized IDs such as `TAT-01`.

Never commit:
- private participant phone numbers;
- private email addresses;
- unnecessary sensitive personal data;
- private client details.

Tattoo portfolio media may contain identifiable bodies/clients. Product design must account for publication permission before public display.

## Scope discipline

- one bounded issue per PR by default;
- search for an existing issue/PR before creating another;
- do not silently broaden scope;
- do not implement postponed work because it seems convenient;
- no unrelated refactors, dependency changes, reformatting or cleanup;
- do not resolve material Founder decisions implicitly;
- if a material unresolved decision blocks work, stop and identify/create the decision gate.

Current explicit non-goals/postponements include, unless later approved:
- public slot picker / full calendar;
- CRM;
- newsletter;
- form builder;
- multi-artist workspace;
- marketplace/public artist directory;
- freeform theme editor;
- generic multi-vertical framework;
- generic rules engine;
- Event/Speaker production code.

## External systems

Repository permission does not imply permission to mutate external systems.

Do not change Production/Preview, payment accounts, hosting, DNS, email, databases, Figma, domains or other external services unless the current task explicitly authorizes that exact mutation.

Never expose credentials or secrets.

## Git / worktree safety

For local implementation work:

- start from current live `main`;
- use a fresh isolated worktree/branch for the task;
- never reuse another task's dirty worktree;
- never delete/reset/clean/stash another task's work;
- never force push unless explicitly authorized;
- inspect existing work before recovering an interrupted session;
- preserve valid already-completed work.

If the requested starting SHA differs from live state, stop and reconcile before editing.

## Tool-routing rule

For substantial local coding that requires Git worktrees, Docker/Testcontainers, repository-local verification, push/PR creation or complex local tooling, prefer **Claude Code Agent on the Founder's Mac**.

ChatGPT may orchestrate/review and is appropriate for:
- research;
- product definition;
- documentation;
- GitHub issue/PR review;
- Figma planning/design work;
- architecture review;
- bounded non-local repository documentation changes.

Do not use tool choice as an excuse to bypass repository rules.

## Verification and PR review

Never rely only on an implementation agent's report.

For implementation PR review, independently verify:
- exact PR head SHA;
- base SHA / current target branch;
- changed files;
- issue scope;
- mergeability;
- auto-merge state;
- exact-head CI;
- substantive implementation for defects CI may miss.

Do not claim a check passed unless it actually ran successfully on the stated head.

If required CI is still running:
- report **PENDING CI** with the incomplete gates;
- stop;
- do not continuously poll.

Resume only when the Founder asks for another status check.

For documentation-only PRs, still verify:
- exact head;
- changed-file list;
- no unrelated product/architecture changes;
- links/identifiers;
- issue/ADR consistency.

## Interrupted-session recovery

After timeout, quota exhaustion, crash or tool interruption:

1. inspect current branch/worktree;
2. determine what already completed;
3. preserve valid prior work;
4. reuse checks that remain valid;
5. rerun only incomplete/invalidated checks;
6. continue from the interruption point.

Never restart a long task blindly.

## Context economy

Begin with:
- this file;
- the linked issue;
- directly relevant ADR/docs/code.

Do not recursively read every document by default.

Read broader context only when a concrete dependency, conflict or uncertainty requires it.

For explicit audit/handoff tasks, a broad read is appropriate.

## Communication

Keep operational responses concise.

Distinguish:
- verified live fact;
- research evidence;
- inference;
- recommendation;
- unresolved Founder decision.

For merge reviews end clearly with either:

**READY FOR FOUNDER MERGE**

or

**DO NOT MERGE**

and state the specific blocker when not ready.
