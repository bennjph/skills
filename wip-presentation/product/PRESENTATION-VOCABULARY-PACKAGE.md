# Presentation Vocabulary Package

**Purpose:** Define the minimum package a project needs so an LLM can generate, extend, and maintain presentations without re-guessing narrative, slide, and visual decisions every session.

## The problem it solves

Presentation models drift for three predictable reasons:

1. they invent a generic deck archetype when the brief is weak
2. they reopen solved visual and writing decisions every session
3. they default to presentation-shaped clichés instead of a real argument

This package makes the presentation system legible to the model and reviewable by the team.

## Package structure

Use this package inside the workspace that owns the deck work.

```text
presentation/
  narrative-thesis.md
  deck-archetype.md
  banned-patterns.md
  title-policy.md
  chart-policy.md
  slide-types.md
  voice-guidelines.md
  prompt-bootstrap.md
  review-checklist.md
  templates/
    deck-brief.md
    slide-contract.md
```

The exact filenames can vary, but the functions should stay stable.

## Layer 1: Narrative thesis

`narrative-thesis.md` defines the deck's central job in one or two sentences.

Example:

`This deck should help an executive team decide to narrow the launch scope to one workflow because the current multi-track plan dilutes adoption and proof.`

Without this, the model falls back to topic coverage.

## Layer 2: Deck archetype

`deck-archetype.md` declares the presentation posture that best fits the job.

Suggested default archetypes:

1. executive decision deck
2. technical review deck
3. investor or pitch deck
4. product strategy deck
5. keynote or narrative reveal deck
6. workshop or collaborative review deck

For incubation, this starter set should be treated as sufficient baseline coverage.
The next work is to harden package shape, clarify overlap boundaries, and only
add new archetypes when repeated comparison work exposes a real gap.
Within this starter set, the executive decision deck should be treated as the
most common working archetype and hardened first.
It should also be defined first as the reference archetype package, with nearby
archetypes clarified against it.

The archetype should pre-answer:

- expected density
- proof style
- appendix depth
- delivery posture
- pacing expectations

For incubation, each archetype package should also carry:

- name
- core job
- best fit
- avoid when
- default audience and stakes pattern
- density profile
- proof style
- pacing
- appendix expectation
- delivery posture
- required slide-role emphasis
- style implications
- nearby archetypes with boundary notes

For the executive decision deck, the first locked `core job` is:

- get a decision, approval, or directional commitment

The first locked `proof style` is:

- decision-grade proof

For the executive decision deck, `density profile` should be handled through
`Organization Variants` (`Org Variants`) rather than one universal default:

- `B2B` or enterprise-leaning org variant: more compressed and proof-dense
- `B2C` or consumer-leaning org variant: lighter, cleaner, and less text-dense on the main path

## Layer 3: Closed slide vocabulary

`slide-types.md` is the allowed set of slide roles and what they mean.

Example slide-role set:

- opener
- context
- tension
- insight
- proof
- comparison
- recommendation
- ask
- appendix evidence

The goal is simple:

reduce slide generation from invention to selection plus adaptation.

## Layer 4: Title policy

`title-policy.md` defines how slide titles behave.

Minimum rules:

- titles state takeaways, not topics
- titles should work in skim mode
- titles should not exceed the deck's density target
- a title must match the slide's actual evidence

This is one of the highest-leverage files in the whole package.

## Layer 5: Writing and voice rules

`voice-guidelines.md` defines the presentation voice.

At minimum, it should specify:

- tone
- sentence density
- preferred proof style
- banned filler language
- speaker-note posture

The goal is not literary style.

The goal is low reader effort and high decision clarity.

## Layer 6: Chart and evidence policy

`chart-policy.md` defines how evidence is shown.

At minimum, it should answer:

- when a chart is justified
- when a table is better than a chart
- how takeaways should be written
- how emphasis should work
- what counts as decorative charting and should be banned

This prevents chart theater.

## Layer 7: Banned patterns

`banned-patterns.md` removes the model's easiest escape hatches.

Examples:

- no topic-only titles
- no agenda slide by default
- no three-box slide by default
- no icon-row filler
- no stock-photo business cliche
- no card wall unless information architecture requires it
- no decorative chart without a takeaway

The point is not style policing.

The point is removing the highest-frequency median patterns.

## Layer 8: Prompt bootstrap

`prompt-bootstrap.md` tells the model how to use the package.

Minimum rule set:

1. read the brief, thesis, and relevant package files before generating
2. choose slide roles from the declared vocabulary
3. apply title policy before body copy
4. prefer appendix moves over overloaded main-story slides
5. keep meaningful text and data editable where the medium allows
6. run the review checklist before considering the work complete

## Acceptance criteria

A project has a usable presentation vocabulary package when:

- one narrative thesis exists
- one deck archetype is chosen
- one closed slide-role vocabulary exists
- title policy is explicit
- banned patterns are explicit
- voice and evidence rules are explicit
- prompt bootstrap explains how the model should operate

## What not to do

Do not mistake a brand deck or slide template for an LLM-readable presentation package.

Do not rely on screenshots alone.

Do not assume a nice-looking PPTX teaches the model how the argument works.

Do not skip the banned list because the deck "looks okay."

## Relationship to the generation loop

This package feeds directly into:

- deck briefs
- prompt bundles
- slide planning
- PPTX generation
- review
- maintenance

It is the presentation equivalent of a closed design system plus operating instructions.
