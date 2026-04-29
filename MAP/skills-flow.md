# Skills Flow Map

> This folder is for the human. Visual reference for how skills connect.

---

## Full Skill Flow

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          BUILD LOOP                                      │
│                                                                          │
│  ┌──────────────────┐                                                  │
│  │ /grill-with-docs  │  Converge plan + domain language                 │
│  │                  │  CONTEXT.md, ADRs, one question at a time         │
│  └──────┬───────────┘                                                  │
│         ▼                                                              │
│  ┌──────────────────┐      ┌─────────────────────┐                     │
│  │ /prototype-data   │ ──── │ /prototype-artifact  │  (optional)       │
│  │ "Define the data" │      │ "Visualize it"       │                     │
│  └──────┬───────────┘      └──────────┬──────────┘                     │
│         ▼                             │                                │
│         └──────────┬──────────────────┘                                │
│                    ▼                                                   │
│  ┌──────────────┐                                                      │
│  │    /to-prd    │  "Write it down" → issue tracker                    │
│  └──────┬───────┘                                                      │
│         ▼                                                              │
│  ┌──────────────┐                                                      │
│  │  /to-issues   │  Vertical slices + "How to verify"                  │
│  └──────┬───────┘                                                      │
│         ▼                                                              │
│  ┌──────────────┐                                                      │
│  │     /tdd      │  Red → Green → Refactor                             │
│  └──────┬───────┘                                                      │
│         │                                                              │
└─────────┼──────────────────────────────────────────────────────────────┘
          ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                       VERIFICATION LOOP                                  │
│                                                                          │
│  ┌──────────────┐                                                        │
│  │   /verify     │  Evidence pack → HTML → human review                 │
│  └──────┬───────┘                                                        │
│         ▼                                                                │
│  ┌──────────────┐                                                        │
│  │ /postmortem   │  Compound learnings into AGENTS.md / rules           │
│  └──────┬───────┘                                                        │
│         │                                                                │
└─────────┼────────────────────────────────────────────────────────────────┘
          ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                     FEEDBACK + MAINTENANCE                               │
│                                                                          │
│  /triage        Issue state machine → agent briefs / needs-info       │
│  /diagnose      Hard bugs: repro loop → fix → regression                │
│        └──────────────────────────────┐                                 │
│                                       ▼                                 │
│                        Back to /grill-with-docs or /tdd as needed       │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────┐
│                        RETROFIT LOOP                                     │
│                                                                          │
│  ┌──────────────────────────────┐                                        │
│  │ /improve-codebase-architecture │  Shallow modules → deepening        │
│  └──────────────────────────────┘                                        │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────┐
│  SETUP (once per repo)     /setup-matt-pocock-skills                    │
└─────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────┐
│                          AD-HOC (anytime)                                │
│                                                                          │
│  /caveman                  Compressed chat mode                         │
│  /design-motion-principles Motion audit                                 │
│  /emil-design-eng          UI polish / craft                            │
│  /familiar                 Familiar stills / recent context            │
│  /zoom-out                 Map module + callers (domain vocabulary)      │
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

- 2026-04-29 — Replaced `/domain-model` + `/grill-me` with `/grill-with-docs`; removed `/qa`, `/design-an-interface`, `/ubiquitous-language` from flow; added `/triage`, `/diagnose`, `/setup-matt-pocock-skills`.
- 2026-04-27 — Added `/familiar` to ad-hoc skills and documented that global sync targets both Codex and Cursor while excluding `wip-presentation/`.
- 2026-04-27 — Added `/emil-design-eng` to ad-hoc skills for UI polish and animation critique.
- 2026-04-27 — Added `/design-motion-principles` to ad-hoc skills for context-aware motion audits.

- 2026-04-19 — Updated: `/to-issues` now shows "How to verify" pre-commit step. `/tdd` now shows visual checkpoint after GREEN. `/verify` and `/postmortem` are now created (not pending). All flow diagrams reflect the verification-first cycle.
