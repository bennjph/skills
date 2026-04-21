# AI Craft Transfer Insights for Presentations

This note captures what is transferable from the `ai-craft` module into the presentation workspace.

It is not a copy of the UI/UX framework.

It is a translation of the useful patterns into presentation generation, deck maintenance, and `.pptx`-specific workflows.

## Main transfer

The strongest idea in `ai-craft` is this:

Prompting is not the bottom layer of quality. It is a middle layer.

Quality improves most when the model is given:

- a clearer thesis
- better intermediate representations
- a closed vocabulary
- stronger negative constraints
- explicit evaluation criteria
- a reusable operating package

This maps extremely well to presentations.

## What transfers cleanly

### 1. Median-output thesis

UI generation falls toward the training-data median.

Presentation generation does too.

In presentation work, the median likely looks like:

- title plus subtitle plus bullet stack
- three-box comparison slides
- generic icon rows
- startup gradients or safe corporate blue
- topic titles instead of action titles
- too many slides with weak narrative compression
- nice-looking but structurally meaningless deck patterns

This is the presentation equivalent of purple-bias SaaS UI.

### 2. Intermediate representations matter more than prompt cleverness

The most transferable `ai-craft` idea is that the model should not invent the product and the UI at the same time.

For presentations, the model should not invent:

- the business logic
- the story sequence
- the slide roles
- the evidence hierarchy
- the visual system

all at the same time inside the final deck.

The presentation equivalents of UI intermediate artifacts are:

- deck brief
- narrative spine
- slide-role map
- prototype JSON
- prototype artifact
- slide contract

### 3. Closed vocabulary packages

The UI system uses a design-system package so the model stops guessing.

Presentation work needs the same move:

- declared narrative posture
- declared slide types
- declared title rules
- declared typography and layout system
- declared chart conventions
- declared banned patterns

Without this, each deck session reopens solved decisions.

### 4. Negative constraints are high leverage

`ai-craft` is right to emphasize bans and anti-default constraints.

That transfers directly.

Presentation generation likely benefits from explicit bans such as:

- no topic-only titles
- no generic agenda slide unless it serves the story
- no icon row filler
- no three-column slide unless the argument requires three peers
- no card wall by default
- no decorative charts without a takeaway
- no stock-photo handshake energy

### 5. Evaluation must diagnose upstream causes

The UI evaluation system is especially transferable.

The key idea is not just to score output.

It is to trace failure back upstream:

- bad prompt
- weak narrative brief
- weak slide contract
- missing data model
- weak design vocabulary
- missing verification

That is exactly the right mentality for a presentation skill that must also support maintenance and updates.

### 6. Package what works

The `ai-craft` system thinks in operating packages instead of one-off heroics.

Presentation work should do the same:

- reuse deck archetypes
- reuse narrative structures by job type
- reuse prompt bundles
- reuse slide contracts
- reuse evaluation checklists

## What does not transfer 1:1

### 1. Browser reality becomes deck reality

UI work uses the browser as the truth surface.

Presentation work needs a different truth surface:

- rendered slides
- editable PPTX structure
- speaker note flow
- slide sorter coherence
- projection and reading conditions

### 2. Components become slide roles and slide contracts

UI generation is heavily component-first.

Presentation generation still benefits from reusable pieces, but the more important unit is often the slide role:

- opener
- context
- proof
- comparison
- recommendation
- appendix evidence

### 3. Interaction state becomes narrative and update state

UI artifacts model hover, focus, loading, error.

Presentations instead need to model:

- audience type
- presenter mode
- live-delivery timing
- appendix spillover
- data-refresh updates
- shortened vs expanded deck versions

### 4. Design-system tokens are necessary but not sufficient

In UI, token discipline can carry a lot.

In presentations, the harder problem is often narrative sequencing, not visual token drift.

The narrative layer deserves even more weight than the visual layer.

## Presentation-specific implications

The transferred system for presentations should likely emphasize:

1. Narrative-first thesis
2. Deck brief and audience fit
3. Structured intermediate artifacts before PPTX
4. Declared slide contracts instead of vague page prompts
5. Native editability and verification
6. Failure-mode diagnosis that points to the right upstream layer

## Strongest ideas worth adopting now

If we adapt only a few things from `ai-craft`, these look highest leverage:

1. Build systems, not decks
2. Use intermediate artifacts before generation
3. Maintain a banned-patterns list
4. Separate prompt-solvable problems from capability gaps
5. Create an evaluation system and failure library

## Design overlap with code generation

The UI/UX material is useful beyond analogy.

There is direct overlap in:

- layout hierarchy
- spacing systems
- typography discipline
- component vocabulary
- state coverage thinking
- visual-system packaging
- anti-slop constraints

This matters because modern presentation generation increasingly overlaps with:

- HTML or React-based previsualization
- structured chart generation
- tokenized design systems
- editable artifact pipelines

So the design-workstream in this presentation workspace should keep borrowing from the UI operating-stack mindset where useful.
