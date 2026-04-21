# Presentation Style Systems

**Purpose:** define the first reusable `Style System` package shape for this repo, seed it with a small initial set, and make the next research steps explicit.

This is not the final style library.

It is the first operating surface that turns the current design-process guidance into reusable systems that the presentation workflow can actually select, compare, and refine.

## Why this file exists

The repo already has:

- strong taste rules
- anti-slop guidance
- a clear distinction between `Deck Archetype` and `Style System`
- a decision to use `Style Pool -> Style System -> Style Variant`

What it did not have yet was the actual package shape for a `Style System`.

This file closes that gap enough to start prototyping.

## What we borrowed from `cowork`

We did not copy `cowork` directly.

We translated the parts that fit presentation work.

### Package shape from `ai-craft`

Useful source:
- `/Users/corphr.software/Documents/cowork/docs/modules/ai-craft/product/LLM-READABLE-DESIGN-SYSTEM-PACKAGE.md`

Transfer:
- a reusable system should have a clear thesis
- it should operate as a closed package, not a mood board
- banned patterns matter as much as positive guidance
- the system should be inspectable and reusable by agents

### Reference families from `design-playground`

Useful sources:
- `/Users/corphr.software/Documents/cowork/docs/modules/design-playground/NEXT-STEPS.md`
- `/Users/corphr.software/Documents/cowork/docs/modules/design-playground/research/ryos-reference-breakdown.md`
- `/Users/corphr.software/Documents/cowork/docs/modules/visual-dev-tooling/use-cases/desktop-prototyping-taste-lab.md`

Transfer:
- use curated reference families instead of generic taste labels
- separate the "median" references from the aspiration bar
- make systems inspectable side by side
- treat the style library as a taste lab, not a static template pile

## Initial `Style System` package shape

Each `Style System` should define these fields:

1. `id`
2. `name`
3. `visual_thesis`
4. `fit_tags`
5. `reference_dna`
6. `typography`
7. `color_system`
8. `grid_and_spacing`
9. `surface_and_shapes`
10. `chart_and_table_treatment`
11. `image_and_diagram_posture`
12. `motion_posture`
13. `title_behavior`
14. `density_profile`
15. `banned_patterns`
16. `best_for`
17. `avoid_when`

This is enough to choose and compare systems before we build a fuller asset library.

## Initial systems

The first style pool should stay small.

Three systems are enough to start:

1. `Editorial Signal`
2. `Operational Clarity`
3. `Premium Narrative`

Why three:

- gives real choice without a style dump
- covers consumer-clean, enterprise-proof, and keynote-premium ranges
- stays reviewable in one side-by-side artifact

## System summaries

### 1. `Editorial Signal`

Core idea:
- typography-first
- minimal color
- sharp hierarchy
- asymmetrical editorial layouts

Best for:
- product strategy decks
- founder/product narratives
- external talks
- clean internal narratives in modern product cultures

Reference DNA:
- Swiss editorial design
- Vercel dashboard restraint
- modern product launch decks

### 2. `Operational Clarity`

Core idea:
- proof-first
- disciplined spacing
- high table and chart readability
- enterprise-safe without looking old

Best for:
- executive decision decks
- internal leadership reviews
- B2B customer and vendor decks
- technical or proof-heavy strategy work

Reference DNA:
- IBM Carbon token discipline
- Stripe dashboard data clarity
- consulting-grade chart restraint

### 3. `Premium Narrative`

Core idea:
- more emotional pacing
- stronger hero moments
- restrained premium visual drama
- still disciplined enough for editable PPTX work

Best for:
- keynote or narrative reveal decks
- investor or launch stories
- high-visibility external talks

Reference DNA:
- keynote reveal pacing
- premium editorial art direction
- presentation hero-slide craft

## Sequential research plan

This is the next research ladder for hardening the style pool.

### Phase 1: seed systems

Done now:
- define package shape
- create first three systems
- render them side by side for critique

### Phase 2: review against real deck jobs

Use the style systems against:
- internal leadership deck
- B2B enterprise pitch
- product-forward consumer-style pitch
- external talk

Main question:
- where does each system clearly fit or fail

Current saved artifacts:
- `/Users/corphr.software/Documents/skills/wip-presentation/artifacts/style-systems-review-2026-04-21.html`
- `/Users/corphr.software/Documents/skills/wip-presentation/artifacts/style-systems-mock-review-2026-04-21.html`
- `/Users/corphr.software/Documents/skills/wip-presentation/models/style-system-mock-decks-v0.json`

Focused deepening completed:
- `Operational Clarity` now has a deeper mock deck review with opener, context, proof, comparison, recommendation, and appendix evidence
- saved at `/Users/corphr.software/Documents/skills/wip-presentation/artifacts/operational-clarity-deep-review-2026-04-21.html`
- canonical source at `/Users/corphr.software/Documents/skills/wip-presentation/models/operational-clarity-deep-mock-v0.json`

This should be treated as saved incubation work for improving the style-system section later, not as final production doctrine.

### Phase 3: expand the asset detail

For the systems that survive review, add:
- typography scale
- slide rhythm patterns
- chart grammar
- table grammar
- section-opener behavior
- appendix posture

### Phase 4: create real variants

Only after a system proves useful:
- create `Style Variant` examples by organization posture or use case

### Phase 5: promotion test

Promote a style rule into the future production skill only if:
- it survives multiple deck jobs
- it reduces editing churn
- it improves quality in review
- it stays understandable to a human operator

## Current status

Status: `working model`

What is stable:
- style systems should be reusable packages
- the first pool should be small
- systems should be previewed side by side

What is still open:
- exact file layout for a mature style library
- full token or master-slide specs per system
- whether these three systems are enough
- which additional systems belong in the next round
