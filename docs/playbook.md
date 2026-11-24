# The solo founder playbook: idea to end users with gstack + Founder skills

This playbook gives the order for running the skills, what each phase needs as input, what it produces, and when the phase is done.
Every skill response worth keeping goes into a markdown file. See [documentation-structure.md](documentation-structure.md).

**Two teams, one founder:**
- **Business team** ([founder-skill](https://github.com/Jakeschincariol/founder-skill)): decides *whether* and *how* to make money. It writes to `founder/`.
- **Engineering team** ([gstack](https://github.com/garrytan/gstack)): decides *what* to build and *how*, then builds, tests and ships it.

---

## Phase 0: Setup (once)

1. Install gstack and the founder skills (see [README](../README.md#quick-start)).
2. Create the project repo and copy in [`project-skeleton/`](../project-skeleton/).
3. Run `/plan-tune` if gstack asks too many questions for your taste.

---

## Phase 1: Idea

| Step | Skill | Why here | Output |
|---|---|---|---|
| 1.1 | `/office-hours` | YC-style questioning. It forces a specific user, a specific pain and the narrowest wedge. | `docs/00-idea/01-office-hours.md` |
| 1.2 | `/founder-board` | Three framework lenses (offer, monopoly, product) score the idea and vote fund / fund if / pass. | `founder/idea.md`, `founder/board.md` |

**Exit criteria:** a one-paragraph problem statement, one named target customer, and the board's "fund if" conditions copied into a checklist.
If the board votes pass, either change the idea and re-run 1.1, or stop. Record the decision.

---

## Phase 2: Validate

Run in this order. Each skill reads the files the earlier ones wrote.

| Step | Skill | Output |
|---|---|---|
| 2.1 | `/founder-competitors` | `founder/competitors.md`: direct, indirect and substitute competitors, prices and complaints |
| 2.2 | `/founder-consumer` (start with `--quick`, then the full 100-buyer run) | `founder/panel/`: who buys, who passes, objections in their own words |
| 2.3 | `/founder-pricing` | Acceptable price range vs. competitors and margin |
| 2.4 | `/founder-offer` | Offer stack that answers the top objections, re-tested on the panel |
| 2.5 | `/founder-cfo` | `founder/cfo.md`: contribution per sale, break-even, year 1, cash needed |

Then copy the conclusions into `docs/01-validation/` (one file per step, numbered).

### ⛔ Gate 1: Build or not?

Write `docs/decisions/0001-build-or-not.md` using [templates/decision-record.md](../templates/decision-record.md). Go only if:
- the panel buy rate is meaningful *and* the objections can be fixed by the offer or the product,
- unit economics are positive at a price the panel accepts,
- you can name at least 5 real people to show the MVP to.

The panel is simulated buyers. Treat its buy rate as an upper bound, not a forecast.

---

## Phase 3: Brand and design system

| Step | Skill | Output |
|---|---|---|
| 3.1 | `/founder-brand` | Name candidates, domain/handle/trademark checks to run, voice, promise |
| 3.2 | `/design-consultation` | Full design system: type, color, spacing, motion, `DESIGN.md` |

**Exit:** a name you have checked yourself (domain bought, handles reserved) and a design system file in the repo.

---

## Phase 4: Plan the MVP

| Step | Skill | Why |
|---|---|---|
| 4.1 | `/plan-ceo-review` | Pushes for the 10-star version, then picks what scope to expand or cut |
| 4.2 | `/plan-design-review` | Rates each UX dimension and fixes the plan before any pixels are made |
| 4.3 | `/plan-eng-review` | Locks architecture, data flow, edge cases, tests |
| 4.4 | `/plan-devex-review` | Only if developers are your users (API, SDK, CLI) |
| 4.5 | `/spec` | Turns the reviewed plan into executable specs / issues |

Shortcut: `/autoplan` runs CEO, design, eng and DX reviews in one pass. Use it for features after the MVP. For the MVP itself, run them one at a time so you can answer each question yourself.

**Outputs:** `docs/03-product/01-mvp.md`, `docs/04-engineering/01-architecture.md`, plus a decision record for each choice that would be hard to undo (stack, database, auth, pricing model).

---

## Phase 5: Build

- Build with Claude Code against the spec, one feature per branch.
- `/design-shotgun` explores UI variants. `/design-html` turns the chosen one into production HTML/CSS.
- `/investigate` when something breaks. Fix root causes, not symptoms.
- `/careful` or `/guard` when working near production data. `/freeze` limits edits to one folder.
- `/context-save` / `/context-restore` between sessions.

---

## Phase 6: Quality

| Step | Skill | When |
|---|---|---|
| 6.1 | `/review` | Every branch, before it lands |
| 6.2 | `/qa` (or `/qa-only` to just report) | Every user-facing change |
| 6.3 | `/design-review` | Every UI change |
| 6.4 | `/cso` | Before the first public launch, then before each major release |
| 6.5 | `/benchmark` | Before launch, then when pages get slow |

Save notable reports to `docs/05-quality/`.

---

## Phase 7: Ship

| Step | Skill |
|---|---|
| 7.1 | `/setup-deploy` (once) |
| 7.2 | `/ship`: tests, version bump, PR |
| 7.3 | `/land-and-deploy`: merge, deploy, verify |
| 7.4 | `/canary`: watch production after the deploy |
| 7.5 | `/document-release`: update README and docs to match what shipped |

Each release gets `docs/06-releases/vX.Y.Z.md`.

---

## Phase 8: Go to market

| Step | Skill | Output |
|---|---|---|
| 8.1 | `/founder-marketing` | Positioning, channels, 30-day dated campaign, 10 hooks, max cost per customer |
| 8.2 | `/founder-ops` | Tools, routines, support, risk register. Real costs go back to the CFO |
| 8.3 | `/founder-launch` | A cheap real-world test first, then the countdown, launch-day run sheet and first 30 days |
| 8.4 | `/founder-plan` | `founder/business-plan.md` with a computed verdict |

You can start 8.1 during Phase 5. Build an audience while you build the product.

### ⛔ Gate 2: Launch or not?

- `/founder-plan` says **Profitable** and the real-world test from 8.3 confirms demand: launch.
- **Not yet**: find the failing number (price, conversion, cost) and go back to Phase 2 for that one skill.
- **Incomplete**: fill the missing inputs and re-run.

---

## Phase 9: The loop (weekly, forever)

1. `/retro`: what shipped, what stalled. Save to `docs/08-retros/YYYY-Www.md`.
2. `/health`: code quality trend.
3. Talk to real users. Put feedback in `docs/03-product/feedback.md`.
4. New feature idea → `/office-hours` → `/autoplan` → Phase 5 → 6 → 7.
5. Pricing or offer change → `/founder-pricing` / `/founder-offer` → `/founder-cfo`.
6. `/learn` to review what gstack has learned about the project.

---

## Cheat sheet

```
/office-hours → /founder-board
→ /founder-competitors → /founder-consumer → /founder-pricing → /founder-offer → /founder-cfo
→ [GATE 1]
→ /founder-brand → /design-consultation
→ /plan-ceo-review → /plan-design-review → /plan-eng-review → /spec
→ build (+ /design-shotgun, /design-html, /investigate)
→ /review → /qa → /design-review → /cso → /benchmark
→ /ship → /land-and-deploy → /canary → /document-release
→ /founder-marketing → /founder-ops → /founder-launch → /founder-plan
→ [GATE 2] → launch
→ weekly: /retro → /health → /office-hours → /autoplan → build → /ship
```
