# My AI Team: a solo founder playbook for gstack + Founder skills in Claude Code

**A step-by-step order for running AI agent skills in Claude Code, from first idea to paying users.**
It combines [gstack](https://github.com/garrytan/gstack) (an engineering team: product, design, eng review, QA, ship) with
[founder-skill](https://github.com/Jakeschincariol/founder-skill) (a business team: board, competitors, consumer panel, pricing, CFO, marketing, launch).
You can use it as a solo founder with no co-founder, no staff and an AI coding agent.

> Keywords: Claude Code skills, gstack workflow, AI solo founder, indie hacker playbook, startup validation with AI,
> AI product development workflow, idea to launch, Claude agents, vibe coding process, documentation structure for AI projects.

---

## The sequence at a glance

```
IDEA ─► VALIDATE ─► BRAND ─► PLAN ─► BUILD ─► SHIP ─► LAUNCH ─► LOOP
```

| # | Phase | Run these skills, in order | Writes to |
|---|---|---|---|
| 0 | Setup | install gstack + founder-skill | none |
| 1 | Idea | `/office-hours` → `/founder-board` | `docs/00-idea/`, `founder/` |
| 2 | Validate | `/founder-competitors` → `/founder-consumer` → `/founder-pricing` → `/founder-offer` → `/founder-cfo` | `founder/`, `docs/01-validation/` |
| ⛔ | **Gate 1** | Go / no-go. Record it in `docs/decisions/` | `docs/decisions/` |
| 3 | Brand & design system | `/founder-brand` → `/design-consultation` | `docs/02-brand-design/` |
| 4 | Plan the MVP | `/plan-ceo-review` → `/plan-design-review` → `/plan-eng-review` (or `/autoplan` for all three) → `/spec` | `docs/03-product/`, `docs/04-engineering/` |
| 5 | Build | code with Claude → `/design-shotgun` / `/design-html` for UI → `/investigate` on bugs | the code |
| 6 | Quality | `/review` → `/qa` → `/cso` → `/design-review` → `/benchmark` | `docs/05-quality/` |
| 7 | Ship | `/ship` → `/land-and-deploy` → `/canary` → `/document-release` | `docs/06-releases/` |
| 8 | Go to market | `/founder-marketing` → `/founder-ops` → `/founder-launch` → `/founder-plan` | `docs/07-marketing/` |
| ⛔ | **Gate 2** | `/founder-plan` verdict = Profitable? Launch. Not yet? Go back to step 2 | `docs/decisions/` |
| 9 | Loop (weekly) | `/retro` → `/health` → new feature: `/office-hours` → step 4 | `docs/08-retros/` |

The rule is to **validate before you build**. The founder skills cost tokens. A wrong product costs months.

Full details for each step, including why it sits where it does and when to skip it, are in **[docs/playbook.md](docs/playbook.md)**.

---

## What's in this repo

| File | What it is |
|---|---|
| [docs/playbook.md](docs/playbook.md) | The full A to Z sequence with inputs, outputs and exit criteria per phase |
| [docs/skills-reference.md](docs/skills-reference.md) | Every gstack and founder skill in one table: what it does and when to run it |
| [docs/documentation-structure.md](docs/documentation-structure.md) | The proposed `docs/` folder for recording skill analysis and decisions |
| [templates/](templates/) | Copy-paste templates: phase doc, decision record (ADR), skill run log, retro |
| [project-skeleton/](project-skeleton/) | An empty `docs/` + `founder/` tree you can copy into a new project |

## Quick start

```bash
# 1. Install gstack (see its repo for the latest instructions)
#    https://github.com/garrytan/gstack

# 2. Install the founder skills as plain /founder-* commands
git clone https://github.com/Jakeschincariol/founder-skill.git
cp -r founder-skill/skills/founder-* ~/.claude/skills/

# 3. Copy the docs skeleton into your new project
cp -r project-skeleton/. /path/to/your-project/

# 4. Open Claude Code in your project and start
/office-hours
```

## Why this order

- **Business before code.** `/office-hours` and the founder board kill bad ideas cheaply. Building comes later.
- **Simulated buyers first, real buyers next.** `/founder-consumer` finds objections fast. `/founder-launch` then tests with real people. Treat the panel's buy rate as an upper bound.
- **Brand before UI.** `/founder-brand` gives `/design-consultation` a name, a voice and a promise, so the design system does not need redoing.
- **Plan reviews before code.** CEO, then design, then engineering. Each step narrows the scope that the next one locks.
- **Ship small, then loop.** `/ship` + `/canary` per change, `/retro` weekly, and new feature ideas go back through `/office-hours`.

## Credits

- [gstack](https://github.com/garrytan/gstack) by Garry Tan. Skills list: [docs/skills.md](https://github.com/garrytan/gstack/blob/main/docs/skills.md)
- [founder-skill](https://github.com/Jakeschincariol/founder-skill) by Jake Schincariol

This repo is only a playbook and a docs structure. It does not include either skill pack.

## License

MIT. See [LICENSE](LICENSE).
