# Skills Flow Map

> This folder is for the human. Visual reference for how skills connect.

---

## Full Skill Flow

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          BUILD LOOP                                      │
│                                                                          │
│  ┌──────────────┐                                                        │
│  │ /domain-model │  "What IS this world?"                                │
│  │              │   CONTEXT.md, ADRs, glossary                           │
│  └──────┬───────┘                                                        │
│         ▼                                                                │
│  ┌──────────────┐                                                        │
│  │   /grill-me   │  "What do we BUILD?"                                  │
│  │              │   One-at-a-time interrogation                          │
│  └──────┬───────┘                                                        │
│         ▼                                                                │
│  ┌──────────────────┐      ┌─────────────────────┐                       │
│  │ /prototype-data   │ ──── │ /prototype-artifact  │  (optional pair)     │
│  │ "Define the data" │      │ "Visualize it"       │                      │
│  └──────┬───────────┘      └──────────┬──────────┘                       │
│         ▼                             │                                  │
│         └──────────┬──────────────────┘                                  │
│                    ▼                                                     │
│  ┌──────────────┐                                                        │
│  │    /to-prd    │  "Write it down"                                      │
│  │              │   Structured PRD from converged decisions              │
│  └──────┬───────┘                                                        │
│         ▼                                                                │
│  ┌──────────────┐                                                        │
│  │  /to-issues   │  "Break into work"                                    │
│  │              │   Vertical slices, each with "How to verify" field     │
│  └──────┬───────┘                                                        │
│         ▼                                                                │
│  ┌──────────────┐                                                        │
│  │     /tdd      │  "Build it"                                           │
│  │              │   Red → Green → Refactor (one test at a time)          │
│  │              │   Visual checkpoint after each GREEN                   │
│  └──────┬───────┘                                                        │
│         │                                                                │
└─────────┼────────────────────────────────────────────────────────────────┘
          ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                       VERIFICATION LOOP                                   │
│                       (manual /slash commands)                            │
│                                                                          │
│  ┌──────────────┐                                                        │
│  │   /verify     │  "Prove it works"                                     │
│  │              │   1. Generate evidence pack (screenshots/video/GIF)    │
│  │              │   2. Agent self-reviews output                         │
│  │              │   3. Fix issues found, regenerate                     │
│  │              │   4. Package into HTML report                          │
│  │              │   5. Human reviews, adds comments                     │
│  └──────┬───────┘                                                        │
│         ▼                                                                │
│  ┌──────────────┐                                                        │
│  │ /postmortem   │  "What did we learn?"                                 │
│  │              │   1. Reflect on session transcript                     │
│  │              │   2. Collect human input                               │
│  │              │   3. Identify DO / DON'T / WHEN patterns              │
│  │              │   4. Propose edits to AGENTS.md or .cursor/rules/     │
│  │              │   5. Human approves each change                       │
│  │              │   6. Apply — repo gets smarter for next run           │
│  └──────┬───────┘                                                        │
│         │                                                                │
└─────────┼────────────────────────────────────────────────────────────────┘
          ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                        FEEDBACK LOOP                                      │
│                                                                          │
│  ┌──────────────┐                                                        │
│  │     /qa       │  "What's broken?"                                     │
│  │              │   Conversational bug reporting                         │
│  │              │   Files durable issues                                 │
│  └──────┬───────┘                                                        │
│         │                                                                │
│         └──────────────────────────────────────┐                         │
│                                                ▼                         │
│                                        Back to /grill-me                  │
│                                        for the fix cycle                  │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────┐
│                        RETROFIT LOOP                                      │
│                                                                          │
│  ┌──────────────────────────────┐                                        │
│  │ /improve-codebase-architecture │  "What's shallow?"                   │
│  │                              │   Survey for architectural friction   │
│  └──────────────┬───────────────┘                                        │
│                 ▼                                                        │
│  ┌──────────────────────────────┐                                        │
│  │    /design-an-interface       │  "Design competing boundaries"       │
│  │                              │   3+ radical interface designs        │
│  └──────────────────────────────┘                                        │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────┐
│                          AD-HOC (anytime)                                 │
│                                                                          │
│  /caveman              Compressed chat mode (~75% fewer tokens)          │
│  /design-motion-principles  Context-aware UI motion audit                │
│  /emil-design-eng      UI polish, component craft, animation critique    │
│  /familiar             Recent screen/session context from Familiar stills │
│  /ubiquitous-language  Batch glossary extraction → UBIQUITOUS_LANGUAGE.md│
│  /zoom-out             Code context map — neighbors, data flow, deps     │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## Verification-First Detail

This is the core loop from Lucas Meyer's verification-first evaluation packs concept. The agent decides how verification will work *before* it starts, then produces evidence the human can review fast.

```
    ┌──────────────────────────────────────────────┐
    │          VERIFICATION-FIRST CYCLE             │
    │                                               │
    │  1. PRE-COMMIT (in /to-issues)                │
    │     ┌─────────────────────┐                   │
    │     │ "How to verify"     │  Written into     │
    │     │ field per slice     │  each work issue  │
    │     └────────┬────────────┘                   │
    │              ▼                                │
    │  2. BUILD (in /tdd)                           │
    │     ┌─────────────────────┐                   │
    │     │ Visual checkpoint   │  After each GREEN │
    │     │ after test passes   │  cycle            │
    │     └────────┬────────────┘                   │
    │              ▼                                │
    │  3. PROVE (in /verify)                        │
    │     ┌─────────────────────┐                   │
    │     │ Generate evidence   │  Screenshots,     │
    │     │ pack by task type   │  video, GIF,      │
    │     │                     │  structured out   │
    │     └────────┬────────────┘                   │
    │              ▼                                │
    │     ┌─────────────────────┐                   │
    │     │ Agent self-reviews  │  Reads own output │
    │     │ → fixes → re-gen    │  iterates         │
    │     └────────┬────────────┘                   │
    │              ▼                                │
    │     ┌─────────────────────┐                   │
    │     │ HTML report saved   │  proofs/ folder   │
    │     │ Human reviews       │                   │
    │     └────────┬────────────┘                   │
    │              ▼                                │
    │  4. LEARN (in /postmortem)                    │
    │     ┌─────────────────────┐                   │
    │     │ Reflect on session  │  Transcript +     │
    │     │ + human feedback    │  evaluation pack  │
    │     └────────┬────────────┘                   │
    │              ▼                                │
    │     ┌─────────────────────┐                   │
    │     │ Compound learnings  │  Edits to         │
    │     │ into instructions   │  AGENTS.md,       │
    │     │                     │  .cursor/rules/   │
    │     └─────────────────────┘                   │
    │                                               │
    └──────────────────────────────────────────────┘
```

---

## Evidence Types by Task Kind

```
    ┌─────────────────────┬──────────────────────────────────────┐
    │ Task Kind           │ Evidence Type                         │
    ├─────────────────────┼──────────────────────────────────────┤
    │ UI interactive flow │ Video recording + key screenshots     │
    │ UI sequential flow  │ GIF of action sequence + screenshots  │
    │ UI static           │ Screenshots at key states             │
    │ API / backend       │ Structured test output + fixture caps │
    │ CLI / terminal      │ Animated GIF of terminal session      │
    │ Docs                │ Rendered diff summary                 │
    │ Data / config       │ Before/after comparison table         │
    └─────────────────────┴──────────────────────────────────────┘
```

---

## Postmortem Learning Targets

The postmortem writes to persistent files that the agent reads automatically on future sessions. This is how the repo compounds knowledge over time.

```
    ┌──────────────────────────────────────────────────────┐
    │              WHERE LEARNINGS GO                       │
    │                                                      │
    │  ┌─────────────────┐    Highest impact               │
    │  │   AGENTS.md      │    Rules the agent follows      │
    │  │   (root or       │    every session                │
    │  │    subdirectory) │                                │
    │  └────────┬────────┘                                 │
    │           │                                          │
    │           ▼                                          │
    │  ┌─────────────────┐    Process observations         │
    │  │  LEARNINGS.md    │    worth keeping, reviewing    │
    │  │  (root)          │    later, promoting to rules   │
    │  └────────┬────────┘                                 │
    │           │                                          │
    │           ▼                                          │
    │  ┌─────────────────┐    Session memory               │
    │  │  sessions/       │    Not auto-read by agent       │
    │  │  context.md      │    Human reference              │
    │  └─────────────────┘                                 │
    │                                                      │
    └──────────────────────────────────────────────────────┘
```

---

## Change Log

- 2026-04-27 — Added `/familiar` to ad-hoc skills and documented that global sync targets both Codex and Cursor while excluding `wip-presentation/`.
- 2026-04-27 — Added `/emil-design-eng` to ad-hoc skills for UI polish and animation critique.
- 2026-04-27 — Added `/design-motion-principles` to ad-hoc skills for context-aware motion audits.

- 2026-04-19 — Updated: `/to-issues` now shows "How to verify" pre-commit step. `/tdd` now shows visual checkpoint after GREEN. `/verify` and `/postmortem` are now created (not pending). All flow diagrams reflect the verification-first cycle.
