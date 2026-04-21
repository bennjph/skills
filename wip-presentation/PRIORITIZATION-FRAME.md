# Prioritization Frame

Use this frame when reviewing each branch. The goal is not to capture every idea. The goal is to sort ideas by value and by the kind of solution they need.

## Classification buckets

### A. Matters

These are high-leverage capabilities or standards that the eventual skill must encode.

Signals:

- materially changes deck quality
- prevents recurring failure
- applies across multiple use cases
- can be taught or enforced with reasonable clarity

### B. Does not matter much

These are ideas that sound sophisticated but do not create enough practical value to deserve instruction weight.

Signals:

- low leverage
- niche edge case
- mostly aesthetic preference
- expensive to encode for limited gain

### C. Generic AI limitation

These are failure patterns that show up when an LLM tries to make decks without enough structure or judgment.

Examples:

- narrative drift
- confident but empty slide copy
- generic layouts that do not fit the job
- inconsistent argument logic across the deck

### D. Solvable with prompts or skill instructions

These problems can likely be improved through better framing, checklists, workflow constraints, or explicit standards.

Examples:

- requiring action titles
- forcing audience and purpose capture before layout
- asking for one message per slide
- banning generic bullet filler

### E. Needs deeper capability

These problems will not be solved well by instructions alone. They need tooling, structured data, verification, runtime support, or human review.

Examples:

- safe PPTX update mechanics
- native chart verification
- accessibility checks
- layout fidelity checks
- high-quality design selection under ambiguity

### F. Constant discovery and evolution

These are areas where the skill will need a living process rather than a one-time rule set.

Examples:

- evolving design taste
- changing audience expectations
- new authoring runtimes
- emerging best practices for review and verification

## Review template

For each branch, write short answers to:

1. What are the highest-leverage ideas here?
2. Which ideas are overvalued and can stay lightweight?
3. Where does generic AI predictably fail?
4. Which failures can be reduced through prompts alone?
5. Which failures need richer capability than prompts can provide?
6. What should remain an ongoing discovery process instead of a fixed rule?

## Decision rule

An idea should not become default skill behavior unless it lands clearly in one of these categories:

- matters and prompt-solvable
- matters and capability-worthy

Everything else stays as reference, optional guidance, or future research.
