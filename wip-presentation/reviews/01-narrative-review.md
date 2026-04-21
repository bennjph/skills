# Branch 1 Review: Narrative Architecture

This is the first sequential review. The purpose is not to finalize instructions. The purpose is to separate high-value narrative requirements from attractive but lower-value ideas.

## Branch claim

Narrative is the highest-leverage branch because most generic AI deck failure starts before design. Weak story logic produces empty titles, unfocused slide sequences, generic layouts, and decks that feel longer than they are.

## What matters

### 1. The skill must identify the decision

The deck should not start from "make slides about X." It should start from "change this audience's understanding or decision in this way."

Why it matters:

- determines what belongs in the deck
- determines what can be cut
- determines whether the output is persuasive, explanatory, or decision-oriented

### 2. The skill must define a controlling idea

There needs to be one central claim or recommendation that the deck is helping the audience accept.

Why it matters:

- prevents slide sprawl
- keeps sections from becoming parallel mini-decks
- improves title writing later

### 3. Slide roles must be explicit

Each slide should have a job:

- context
- tension
- insight
- proof
- recommendation
- ask

Why it matters:

- exposes redundant slides early
- reduces contradiction across the deck
- creates a stable basis for later updates

### 4. The deck must work in skim mode

If the action titles or slide summaries do not tell a coherent story on their own, the narrative is weak.

Why it matters:

- reflects executive reading behavior
- exposes gaps before visual polish hides them
- acts as a practical quality gate

### 5. Appendix discipline matters

Main-story slides and backup material should be separated on purpose.

Why it matters:

- prevents overloaded decks
- protects pacing
- keeps proof available without collapsing the main narrative

## What does not matter much

### 1. Over-theorizing story frameworks

The skill does not need ten named frameworks. It needs one or two durable structures that help make better decks.

### 2. Over-optimizing dramatic arc for every deck

Some decks are high-theater keynotes. Many are not. The skill should support tension and payoff, but not force cinematic storytelling where a clear decision memo style is better.

### 3. Trying to fully automate strategic judgment

The skill can improve structure, but it should not pretend to replace human strategic ownership of the message.

## Generic AI limitations in this branch

### 1. AI confuses topic coverage with narrative

It often produces a complete-sounding deck that includes all the expected sections but never lands a clear argument.

### 2. AI smooths contradictions instead of resolving them

It can generate locally plausible slides that do not line up globally.

### 3. AI inflates deck length

Without strong constraints, it adds slides because more content feels safer than sharper content.

### 4. AI struggles with audience-specific persuasion

It often sounds generally competent rather than precisely tuned to investor, executive, or technical scrutiny.

### 5. AI does not naturally know what to cut

Removal is harder than expansion. Generic models are much better at adding than subtracting.

## What prompts and skill instructions can solve

### 1. Force audience and decision capture first

This is promptable and should probably be mandatory.

### 2. Require a controlling idea before slide generation

Also promptable. The skill can refuse to proceed without a crisp message statement in ambiguous cases.

### 3. Require action titles or slide-level claims

This is a strong instruction-level intervention.

### 4. Require a slide-role map

A simple schema like `context -> tension -> insight -> proof -> ask` can improve coherence significantly.

### 5. Ask for cut candidates

The skill can explicitly identify slides or sections that are likely expendable before deck build.

## What needs deeper capability than prompts alone

### 1. Cross-slide consistency checking

Prompting helps, but reliable contradiction detection across a longer deck likely needs structured representations and review passes.

### 2. Audience-fit evaluation

A prompt can say "optimize for executives," but real quality may need examples, review criteria, or human validation.

### 3. Narrative verification after updates

When numbers, sections, or audience change, the skill needs a way to re-check whether the story still holds. That suggests structured slide plans and explicit verification, not just better wording.

## Constant discovery and evolution

### 1. Different professionals tell stories differently

Consulting-style decks, founder decks, keynote decks, and architecture reviews should not collapse into one narrative voice.

### 2. The right level of narrative force varies by use case

Sometimes the job is persuasion. Sometimes it is explanation. Sometimes it is alignment. The skill should keep learning where hard narrative pressure helps and where it distorts.

### 3. Human taste about "too much story" will vary

This branch will always need some human prioritization because the right amount of framing and drama depends on audience culture.

## Provisional takeaways

If we prioritize aggressively, the narrative branch should probably encode these first:

1. Audience plus decision capture
2. Controlling idea
3. Slide-role map
4. Action-title skim test
5. Main-story versus appendix separation

Everything else in this branch should be treated as secondary until these are working.

## Questions for prioritization

These are the decisions you likely need to make before we freeze this branch:

1. Should the future skill require a decision statement, or just strongly prefer it?
2. Do you want a single default narrative structure, or a small menu by use case?
3. How opinionated should the skill be about cutting slides and moving material to appendix?
