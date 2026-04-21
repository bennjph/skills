# Sequential Research Order

This file defines the order in which we should research and review the presentation skill branches.

The goal is to avoid premature synthesis. We want to understand each branch well enough to classify:

- what matters
- what does not matter
- what generic AI is weak at
- what prompt instructions can improve
- what needs deeper tooling, workflows, or ongoing discovery

## Recommended order

### 1. Narrative architecture

Reason: if the story logic is weak, every downstream branch becomes cleanup work. This is the root branch.

Main questions:

- What is the actual decision or change the deck must drive?
- What makes a narrative coherent across slides?
- What narrative mistakes are structural rather than stylistic?
- Which narrative failures are common with generic AI?

### 2. Writing style and message compression

Reason: once the story is right, the next major risk is weak language. Generic AI often sounds polished while saying very little.

Main questions:

- What writing rules reliably improve slide clarity?
- Which rewriting tasks are prompt-solvable?
- What kinds of message compression need human judgment?

### 3. Design process and taste

Reason: only after message and language are stable does it make sense to define visual standards. Design should serve meaning rather than compensate for missing structure.

Main questions:

- What is actually teachable as instructions?
- What is taste calibration versus hard rule?
- Which deck-design patterns should be actively banned?

### 4. Prototype-first JSON workflow

Reason: once we understand the story and design questions, we can define the right pre-PPTX planning surface.

Main questions:

- What structure should be modeled before deck creation?
- What is worth rendering as a prototype artifact?
- What is cheap to iterate in JSON and expensive to change in PPTX?

### 5. Technical PPTX CRUD

Reason: the file-format and tooling layer should serve the higher-level workflow, not define it too early.

Main questions:

- What operations must the skill support reliably?
- What is promptable versus what needs runtime capabilities?
- Where do update safety and verification become critical?

## Review output for each branch

Every branch review should end with five outputs:

1. What matters
2. What does not matter
3. What generic AI is bad at here
4. What prompts can probably solve
5. What requires deeper capability or ongoing discovery

## Decision rule

Do not fold a branch into the actual skill until you have reviewed and prioritized the branch explicitly.
