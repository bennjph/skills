# Elite Presentation Engineering Synthesis

This note compresses the research input into working guidance for a presentation skill.

## Main claim

Elite presentation work is not slide decoration. It is a compound discipline that combines strategy, narrative design, information design, and PPTX engineering. The visible slides are the artifact. The real skill is deciding what story should exist, what should be cut, how evidence should be sequenced, and how the deck should remain editable and robust.

## The central failure mode to avoid

The common AI failure is not ugly slides. It is empty structure:

- generic boxes and icons
- bullets that sound competent but do not move the argument
- too many slides for too little message
- weak internal logic across the deck
- no sense of what the audience must believe, decide, or do next

The practical implication for the skill is clear: do not let deck generation start from layout alone. Force the message and decision path into the workflow first.

## What elite practitioners actually do

- Start with the audience, stakes, and decision.
- Form a top-down message architecture before designing slides.
- Use action titles so the deck can be skimmed as a narrative.
- Control density so each slide can be understood quickly.
- Build on templates, master layouts, and constrained systems instead of freestyle sprawl.
- Make charts, diagrams, and text editable whenever possible.
- Use motion and polish only when they sharpen understanding.

## Non-negotiable standards

### Narrative

- Every deck needs a point, not just a topic.
- Every slide needs a role in the argument.
- Action titles should carry the story if read in sequence.
- The presentation should feel shorter than it is because the logic is clean.

### Cognitive load

- One message per slide is the default.
- Dense ideas should be split, not squeezed.
- White space is functional, not ornamental.
- If a slide takes too long to decode, it should be redesigned or broken apart.

### Design system

- Use strong grids, consistent margins, and explicit alignment rules.
- Favor flush-left hierarchy and deliberate grouping over centered decoration.
- Prefer structural components and reusable patterns over one-off artistry.
- Keep color, typography, and spacing opinionated enough to prevent drift.

### Technical integrity

- Treat `.pptx` as a structured document, not a flat image sequence.
- Preserve editable text, chart, and table objects when possible.
- Use theme and layout systems instead of manual per-slide cleanup.
- Anticipate update operations, not just first-pass generation.

### Quality constraints

- Keep accessibility, contrast, and reading order in scope.
- Avoid file bloat and fragile media handling.
- Ensure the deck survives handoff and edits by a non-designer.

## Capability map

The skill needs five cooperating capabilities:

1. Narrative architecture
2. Writing and message compression
3. Design-system and layout judgment
4. PPTX CRUD and verification mechanics
5. Prototype-first exploration using structured JSON and visual artifacts

If any one of these is weak, the output degrades:

- no narrative -> beautiful nonsense
- no writing discipline -> smart-sounding sludge
- no design system -> inconsistent amateur slides
- no PPTX engineering -> brittle deck that cannot be safely updated
- no prototype loop -> expensive iteration inside the final file format

## Implications for the new skill

- The skill should behave more like a narrative architect plus deck engineer than a graphic decorator.
- It should ask sharper questions about audience, purpose, and decision than a generic slide generator would.
- It should create structured intermediate artifacts before touching the final deck.
- It should verify both visible quality and editable document integrity.
- It should explicitly guard against the recognizable AI deck smell.
