# Claude Code — Tessnova

@AGENTS.md

## Start here

Before non-trivial work, read:

1. `AGENTS.md`
2. the linked GitHub issue
3. directly relevant accepted ADR/product docs
4. approved Figma when the task changes UX/UI
5. only the additional files required by concrete dependencies

Do not jump from a broad request directly to code.

## Current gate

M0–M3 are complete. M4 Technical Architecture planning is active.

Production implementation is not authorized. M5 remains gated. Verify live roadmap Issue #1 before every implementation request.

## Local implementation workflow

When implementation is authorized:

1. fetch/inspect current live `main`;
2. verify the requested starting SHA;
3. create a fresh isolated worktree;
4. keep one bounded issue/PR;
5. preserve existing dirty/in-progress worktrees;
6. run focused tests/checks first;
7. run required final repository verification when stable;
8. review diff for scope creep;
9. commit and push the bounded branch;
10. open PR when authorized;
11. inspect exact-head CI once;
12. if CI is pending, report pending jobs and stop;
13. never merge or enable auto-merge.

## Product/architecture guardrails

Do not:
- generalize Tattoo features for hypothetical future verticals;
- add a `vertical` column because the product may expand later;
- build generic capability/rules engines;
- add Tattoo domain components to Nova UI;
- modify Klinnova or Slotnova unless explicitly scoped;
- execute M4 technical architecture as production implementation, or treat an unapproved ADR/option as a selected stack.

## Skills / execution techniques

Use planning, TDD, systematic debugging, accessibility review and frontend design skills selectively when they materially improve the bounded task.

Skills are execution aids, not sources of product truth.

Founder decisions, repository rules, accepted ADRs, approved Figma and the linked issue always outrank agent heuristics.

## Review output

For read-only reviews, report findings with:
- severity: blocker / high / medium / low;
- exact path;
- concrete problem;
- impact;
- minimal correction.

Also state what is correct and should remain unchanged.

Never merge.
