# Presentation Operating Stack

**Purpose:** Adapt the `ai-craft` operating-stack model to elite presentation creation, generation, update, and maintenance.

## Core claim

Strong AI-generated presentations do not come from better prompt wording alone.

They come from moving the inputs closer to presentation reality before deck generation starts.

That means:

- define the decision and narrative thesis before slides
- model the deck structure before the PPTX
- give the model a closed presentation vocabulary
- generate against slide contracts, not vague page descriptions
- verify editability and narrative coherence, not just screenshots

Prompting still matters.

It sits in the middle of the stack, not at the bottom of it.

## The stack

| Layer | Question it answers | Primary artifact |
| --- | --- | --- |
| **1. Decision and narrative thesis** | What change should this deck create in this audience? | deck brief, decision statement, narrative thesis |
| **2. Reality model** | What data, claims, risks, and evidence define the deck? | structured brief, realistic content, evidence map |
| **3. Narrative and visual plan** | What slide sequence, roles, and pacing should exist? | prototype JSON, artifact, slide-role map |
| **4. Presentation vocabulary** | Which style, title rules, chart rules, and banned patterns are already decided? | presentation system package |
| **5. Slide contracts** | What must each slide type do, show, and handle? | slide spec by role and state |
| **6. Generation and update surface** | Which tool should generate, revise, or patch the deck? | prompt bundle, tool choice, update instructions |
| **7. Editable deck reality** | Does the deck hold up as a real `.pptx` file? | rendered previews, deck inspection, editable objects |
| **8. Evaluation and maintenance** | How do we score quality, diagnose drift, and support future edits? | rubric, failure library, maintenance checks |

## Prompting's actual place

Prompting belongs across Layers 4 through 6.

It binds:

- the deck brief
- the narrative and visual plan
- the presentation vocabulary
- the slide contracts
- the chosen generation surface

When those layers are weak, the prompt carries too much weight and the output drifts toward the median.

When those layers are strong, the prompt becomes shorter, clearer, and more stable.

## The operating loop

1. Define the audience, decision, and narrative thesis.
2. Build the reality model with realistic evidence, claims, and constraints.
3. Create the narrative and visual plan as structured artifacts.
4. Prepare the presentation vocabulary package.
5. Write slide contracts for the slide roles that matter.
6. Generate or update the deck using the chosen authoring surface.
7. Inspect the rendered deck and the editable deck structure.
8. Score the output with the evaluation system.
9. Fix the upstream artifact that caused the problem instead of only patching the visible slide.
10. Package what worked so future deck runs start from stronger priors.

## What to standardize

Standardize these across the presentation workspace:

- deck brief template
- narrative thesis shape
- prototype JSON shape for decks
- slide-role taxonomy
- presentation vocabulary package structure
- slide contract template
- evaluation rubric
- failure-mode vocabulary

Leave these project-specific:

- audience
- presenter voice
- business context
- data inputs
- visual posture
- final tool choice

## Why this matters for maintenance

The same stack that improves generation also improves updates.

If a future request says:

- shorten this deck from 14 slides to 7
- adapt it from investor audience to internal leadership
- update Q2 metrics and keep the story intact
- convert key evidence into appendix slides

then the stack gives the model something more stable to operate on than raw slide surfaces.

## Relationship to current workspace docs

- [narrative-architecture.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/narrative-architecture.md) informs Layers 1 and 3.
- [prototype-json-pipeline.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/prototype-json-pipeline.md) informs Layers 2 and 3.
- [design-process.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/design-process.md) informs Layer 4.
- [technical-crud-pptx.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/technical-crud-pptx.md) informs Layers 6 and 7.
- [writing-style-guidelines.md](/Users/corphr.software/Documents/skills/wip-presentation/workstreams/writing-style-guidelines.md) informs Layers 1, 4, and 5.

## What still has to be proven

- no cross-model benchmark yet for the same deck brief
- no validated presentation shortcut dictionary yet
- no tested threshold for what counts as strong deck quality
- no proven transfer set from UI-generation constraints into presentation-generation constraints

This stack is a first operating model, not a validated final system.
