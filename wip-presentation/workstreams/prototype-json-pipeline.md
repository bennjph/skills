# Prototype: JSON Before PPTX

This workstream defines how `prototype-data` and `prototype-artifact` should feed the presentation skill.

## Why this matters

Deck work becomes expensive when narrative and layout questions are first discovered inside the final `.pptx` file. The prototype loop should absorb the messy exploration earlier.

The goal is not to replace presentations with JSON. The goal is to create a cheap intermediate source of truth that helps us decide what the deck should be before we author it.

## Default pipeline

1. Capture the presentation job.
2. Model it as structured JSON.
3. Render that JSON into an inspectable artifact.
4. Review the artifact for story, density, and sequence.
5. Convert the approved structure into a slide plan.
6. Build the final deck.

## What the JSON should capture

### Deck brief

- presentation type
- audience
- presenter
- decision or outcome needed
- tone and stakes
- time limit

### Narrative spine

- core message
- tension or problem
- supporting claims
- objections
- proof points
- closing ask

### Slide plan

- slide id
- slide role
- action title
- supporting evidence
- visual intent
- speaker note summary

### Design constraints

- brand or style cues
- typography direction
- density tolerance
- accessibility requirements
- required charts, tables, or screenshots

### Update scenarios

- new numbers arrive
- audience changes from technical to executive
- shorten from 12 slides to 6
- convert artifact into appendix-heavy internal version

## What to render before deck creation

The prototype artifact does not need production polish. It needs to expose decisions.

Strong render targets for this skill:

- slide-sequence map
- argument flowchart
- role-based deck blueprint
- sample slide cards with action titles and evidence slots
- timing and pacing view for live delivery

## Review questions for the prototype stage

- If we only read the titles, does the story hold?
- Is each slide doing one clear job?
- Where is the decision point?
- Which slides are proof and which are framing?
- What can be cut with minimal narrative damage?
- Which slides should become appendices?

## Rules for the future skill

- Prototype JSON is the planning source of truth until the deck plan is approved.
- Visual artifacts are for inspection and iteration, not final delivery.
- The skill should be able to regenerate the artifact after narrative changes.
- The deck build should consume structured slide-plan data rather than raw prose blobs.

## What success looks like

Before touching PowerPoint tooling, we should already know:

- who the deck is for
- what the audience should leave believing
- why each slide exists
- what style direction fits the job
- what updates are likely later
