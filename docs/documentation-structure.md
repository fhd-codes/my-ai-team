# Documentation structure for skill output and decisions

Skill responses disappear when the chat ends. This structure records the parts worth keeping: what a skill found, and what you decided because of it.

It follows the IssuePulse layout: numbered files inside topic folders, plus a `founder/` folder that the founder skills manage themselves. It adds two things that layout lacked: a phase-ordered top level, and a single `decisions/` log.

```
your-project/
├── founder/                      # Owned by founder-skill. Let the skills write here.
│   ├── idea.md  board.md  competitors.md  cfo.md  numbers.json
│   ├── panel/                    # consumer panel briefs and answers
│   └── business-plan.md
│
└── docs/
    ├── README.md                 # Index: current phase, latest decision, links
    ├── 00-idea/
    │   └── 01-office-hours.md
    ├── 01-validation/            # Your summary of each founder skill run
    │   ├── 01-board.md
    │   ├── 02-competitors.md
    │   ├── 03-consumer-panel.md
    │   ├── 04-pricing.md
    │   ├── 05-offer.md
    │   └── 06-unit-economics.md
    ├── 02-brand-design/
    │   ├── 01-brand.md
    │   └── 02-design-system.md   # or link to DESIGN.md at the repo root
    ├── 03-product/
    │   ├── 01-mvp.md             # after /plan-ceo-review + /plan-design-review
    │   ├── 02-v1-features.md
    │   └── feedback.md           # real user feedback, dated
    ├── 04-engineering/
    │   ├── 01-stack.md
    │   ├── 02-architecture.md    # after /plan-eng-review
    │   └── specs/                # output of /spec, one file per feature
    ├── 05-quality/               # notable /qa, /cso, /benchmark reports
    ├── 06-releases/
    │   └── v1.0.0.md
    ├── 07-marketing/
    │   ├── 01-positioning.md
    │   ├── 02-launch-plan.md
    │   └── channels/             # reddit.md, x.md, ...
    ├── 08-retros/
    │   └── 2026-W48.md
    ├── decisions/                # One file per decision. Never edit old ones; supersede them.
    │   ├── 0001-build-or-not.md
    │   └── 0002-pick-stack.md
    └── skill-runs/               # Optional raw log: one line per skill run
        └── log.md
```

## Rules

1. **Number files in the order they happened** (`01-`, `02-`). The folder then reads as a story, like `issuepulse/docs/development/`.
2. **Analysis and decisions are separate.** A phase doc says *what the skill found*. A decision record says *what you chose and why*. Link one to the other.
3. **One decision per file**, in `docs/decisions/NNNN-short-title.md` (see [templates/decision-record.md](../templates/decision-record.md)). When you change your mind, write a new record with `Supersedes: 0003`, and set the old one to `Status: Superseded`.
4. **Summarize, don't paste.** Keep the skill's verdict, the numbers, the top 3 to 5 findings and your next action. Paste raw output only when the numbers matter (CFO, pricing).
5. **Every phase doc starts with a status line**: `Status: Draft | Decided | Built | Shipped | Dropped`. That is the same habit as `**Status:** ✅ Built and working` in IssuePulse.
6. **`founder/` belongs to the skills.** Don't hand-edit it. Put your own notes in `docs/01-validation/`.
7. **Keep `docs/README.md` current**: the phase you are in, the last 3 decisions, and the next skill to run.

## Prompt to make Claude record it for you

Add this to your project's `CLAUDE.md`:

```markdown
## Recording skill output
After any gstack or founder skill finishes:
- Summarize the result into the matching docs/ phase folder using templates/phase-doc.md.
- If I made a choice, write docs/decisions/NNNN-title.md using templates/decision-record.md.
- Append one line to docs/skill-runs/log.md: date | skill | one-line result | file written.
- Update docs/README.md "Current phase" and "Next skill".
```

The [project-skeleton/](../project-skeleton/) folder contains this tree with starter files.
