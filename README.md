# Cursor Skills

A collection of agent skills for [Cursor](https://cursor.sh) that form a structured build-verify-learn loop. Each skill is a self-contained `SKILL.md` that the agent reads on demand via slash command.

## Quick Start

1. Clone this repo into `~/.cursor/skills/` (or symlink it there)
2. In a Cursor chat, type the slash command for the skill you want (e.g. `/tdd`, `/grill-me`)
3. The agent reads the skill file and follows its instructions for that session

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
- **Compound learning.** Postmortems write back to `AGENTS.md` and `.cursor/rules/`. The repo gets smarter every session.
- **Tracer-bullet cuts.** Every slice goes end-to-end. No horizontal layer-by-layer work.
- **Human at the seams.** Skills classify work as HITL (human-in-the-loop) or AFK (agent can run alone). Humans approve learning proposals before they're applied.

## Structure

```
~/.cursor/skills/
├── MAP/                              # Human reference maps
│   ├── skills-flow.md                # ASCII flow diagrams
│   └── skills-readme.md              # Detailed skill inventory
├── caveman/SKILL.md
├── design-an-interface/SKILL.md
├── domain-model/SKILL.md
│   ├── CONTEXT-FORMAT.md
│   └── ADR-FORMAT.md
├── grill-me/SKILL.md
├── improve-codebase-architecture/
│   ├── SKILL.md
│   └── REFERENCE.md
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
└── zoom-out/SKILL.md
```

## License

MIT
