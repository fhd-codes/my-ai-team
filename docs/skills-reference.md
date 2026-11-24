# Skills reference

Every skill used in the [playbook](playbook.md), grouped by job. Phase numbers refer to the playbook.

## Founder skills (business team)

Source: [Jakeschincariol/founder-skill](https://github.com/Jakeschincariol/founder-skill). The skills read and write `founder/` in your project.

| Skill | Role | What it gives you | Phase |
|---|---|---|---|
| `/founder-board` | Board of directors | Idea scored through offer, monopoly and product lenses. Vote plus conditions | 1 |
| `/founder-competitors` | Competitor scout | Competitors, prices, positioning, customer complaints, with links | 2 |
| `/founder-consumer` | Consumer panel | 100 simulated buyers: who buys, why not, what flips a no | 2 |
| `/founder-pricing` | Pricing strategist | Acceptable price range (Van Westendorp) vs. competitors and margin | 2 |
| `/founder-offer` | Offer architect | Bonuses, guarantee, urgency, name. Re-tested on the panel | 2 |
| `/founder-cfo` | CFO | Unit economics, break-even, year 1 by month, cash needed, payback | 2 |
| `/founder-brand` | Brand designer | Names, checks to run, voice, promise, look brief | 3 |
| `/founder-marketing` | Marketing director | Positioning, channels, 30-day campaign, hooks, max CAC | 8 |
| `/founder-ops` | Operations manager | Tools, routines, risks, real costs | 8 |
| `/founder-launch` | Launch lead | Real-world test, countdown, launch run sheet, first 30 days | 8 |
| `/founder-plan` | Business planner | Business plan plus computed verdict: Profitable / Not yet / Incomplete | 8 |

## gstack (engineering team)

Source: [garrytan/gstack](https://github.com/garrytan/gstack), [skills list](https://github.com/garrytan/gstack/blob/main/docs/skills.md).

### Think and plan
| Skill | What it does | Phase |
|---|---|---|
| `/office-hours` | YC-style questioning of an idea or feature | 1, 9 |
| `/plan-ceo-review` | Founder-mode scope review: expand, hold or cut | 4 |
| `/plan-design-review` | Designer's review of the plan, before any pixels exist | 4 |
| `/plan-eng-review` | Architecture, data flow, edge cases, tests | 4 |
| `/plan-devex-review` | Developer experience review (APIs, SDKs, CLIs) | 4 |
| `/autoplan` | Runs all plan reviews in one pass | 4, 9 |
| `/spec` | Vague intent to executable spec or issue | 4 |

### Design
| Skill | What it does | Phase |
|---|---|---|
| `/design-consultation` | Builds a full design system | 3 |
| `/design-shotgun` | Several UI variants plus a comparison board | 5 |
| `/design-html` | Final design to production HTML/CSS | 5 |
| `/design-review` | Visual QA of the live UI, with fixes | 6 |

### Build and fix
| Skill | What it does | Phase |
|---|---|---|
| `/investigate` | Root-cause debugging | 5 |
| `/careful`, `/guard`, `/freeze`, `/unfreeze` | Safety rails and edit scope | 5 |
| `/context-save`, `/context-restore` | Carry work across sessions | 5 |
| `/browse` | Real browser for the agent | 5, 6 |

### Quality
| Skill | What it does | Phase |
|---|---|---|
| `/review` | Pre-landing diff review | 6 |
| `/qa`, `/qa-only` | Test the app and fix (or only report) bugs | 6 |
| `/cso` | Security audit | 6 |
| `/benchmark` | Performance regressions | 6 |
| `/health` | Code quality dashboard | 9 |

### Ship and operate
| Skill | What it does | Phase |
|---|---|---|
| `/setup-deploy` | Configure deployment once | 7 |
| `/ship` | Tests, version bump, PR | 7 |
| `/land-and-deploy` | Merge, deploy, verify | 7 |
| `/canary` | Post-deploy monitoring | 7 |
| `/document-release` | Sync docs with what shipped | 7 |
| `/retro` | Weekly retrospective | 9 |
| `/learn` | Review the project learnings gstack has recorded | 9 |

Skill names change between versions. Check each repo's README if a command is missing.
