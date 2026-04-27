# Codex and Cursor Skills

My personal collection of agent skills for Codex and Cursor. Shaped and inspired by https://github.com/mattpocock/skills/tree/main and practices from others, modified and used for my context.

## Quick Start

Install the non-WIP skill folders into both global agent skill locations:

- Codex: `~/.codex/skills/`
- Cursor: `~/.cursor/skills/`

`wip-presentation/` is intentionally excluded until the presentation/PPT generation work is ready.


## Skills

### Build Loop

The main sequence. Walk these in order for new features or modules.

| Command | Purpose | Trigger |
|---|---|---|
| `/domain-model` | Define the domain — glossary, ADRs, CONTEXT.md | Starting a new project or module |
| `/grill-me` | Interrogate a plan — one question at a time | Have a rough idea, need to converge |
| `/prototype-data` | Generate structured JSON data model | Need to define what the feature IS |
| `/prototype-artifact` | Visualize data as flowcharts, mockups | Have JSON data, want visual reference |
| `/to-prd` | Synthesize decisions into a PRD | Decisions converged, time to spec |
| `/to-issues` | Slice PRD into vertical work tickets | Have a PRD, ready to break into work |
| `/tdd` | Red-green-refactor build loop | Have issues, time to code |

### Verification Loop

After building. Manually invoked.

| Command | Purpose | Trigger |
|---|---|---|
| `/verify` | Generate evidence pack — prove it works | After building a feature |
| `/postmortem` | Compound learnings into persistent rules | After a session wraps up |

### Feedback Loop

After shipping. Catches what slipped through.

| Command | Purpose | Trigger |
|---|---|---|
| `/qa` | Conversational bug reporting and issue filing | Something broke in production |

### Retrofit Loop

When existing code needs improvement, not new features.

| Command | Purpose | Trigger |
|---|---|---|
| `/improve-codebase-architecture` | Survey for shallow modules and friction | Inherited a codebase |
| `/design-an-interface` | Generate 3+ competing interface designs | Need to reshape a module boundary |

### Ad-hoc

Anytime. No fixed position in the flow.

| Command | Purpose | Trigger |
|---|---|---|
| `/caveman` | Compressed chat mode (~75% fewer tokens) | Want terse output |
| `/design-motion-principles` | Context-aware motion and interaction design audit | Reviewing UI animations and transitions |
| `/emil-design-eng` | UI polish, component craft, and animation review | Need design-engineering taste checks |
| `/familiar` | Reconstruct recent on-screen work from Familiar stills | Need recent screen/session context |
| `/ubiquitous-language` | Batch extract glossary terms | Term confusion in conversation |
| `/zoom-out` | One-level-up code context map | Deep in a file, lost the neighborhood |

## Flow Map

```
BUILD LOOP
  /domain-model → /grill-me → [/prototype-data → /prototype-artifact] → /to-prd → /to-issues → /tdd
                                                                                                  │
                                                                                                  ▼
VERIFICATION LOOP
  /verify → /postmortem ──────────────────────────────────────────────────────────────────────────┘
                                                                                                  │
                                                                                                  ▼
FEEDBACK LOOP
  /qa ──→ back to /grill-me for the fix cycle
```

The full ASCII flow map with verification-first detail lives in [`MAP/skills-flow.md`](MAP/skills-flow.md). A detailed inventory of every skill is in [`MAP/skills-readme.md`](MAP/skills-readme.md).

## Principles

- **Verification-first.** Define how to verify before building. Each work slice carries its own "How to verify" field.
- **Compound learning.** Postmortems write back to persistent repo instructions. The repo gets smarter every session.
- **Tracer-bullet cuts.** Every slice goes end-to-end. No horizontal layer-by-layer work.
- **Human at the seams.** Skills classify work as HITL (human-in-the-loop) or AFK (agent can run alone). Humans approve learning proposals before they're applied.

## Structure

```
skills repo source/
├── MAP/                              # Human reference maps
│   ├── skills-flow.md                # ASCII flow diagrams
│   └── skills-readme.md              # Detailed skill inventory
├── caveman/SKILL.md
├── design-an-interface/SKILL.md
├── design-motion-principles/
│   ├── SKILL.md
│   └── references/
├── domain-model/SKILL.md
│   ├── CONTEXT-FORMAT.md
│   └── ADR-FORMAT.md
├── emil-design-eng/SKILL.md
├── familiar/SKILL.md
├── grill-me/SKILL.md
├── improve-codebase-architecture/
│   ├── SKILL.md
│   ├── DEEPENING.md
│   ├── INTERFACE-DESIGN.md
│   └── LANGUAGE.md
├── postmortem/SKILL.md
├── prototype-artifact/SKILL.md
├── prototype-data/SKILL.md
├── qa/SKILL.md
├── tdd/
│   ├── SKILL.md
│   ├── deep-modules.md
│   ├── interface-design.md
│   ├── mocking.md
│   ├── refactoring.md
│   └── tests.md
├── to-issues/SKILL.md
├── to-prd/SKILL.md
├── ubiquitous-language/SKILL.md
├── verify/SKILL.md
├── zoom-out/SKILL.md
└── wip-presentation/                 # Excluded from global sync for now
```

## License

MIT
