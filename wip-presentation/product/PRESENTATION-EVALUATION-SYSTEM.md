# Presentation Evaluation System

**Purpose:** Make quality judgment explicit for AI-generated presentations and `.pptx` maintenance work.

This document combines two things:

- a scoring rubric
- a failure-mode library

Use the rubric to judge the deck.

Use the failure library to find the upstream cause and improve the next run.

## Part 1: Presentation quality rubric

### Scoring scale

Score each category from `0` to `4`.

- `0` = broken or missing
- `1` = weak, generic, or misleading
- `2` = acceptable working draft
- `3` = strong and deliberate
- `4` = professional and reusable

Multiply each score by the category weight.

### Rubric

| Category | Weight | What `0` looks like | What `2` looks like | What `4` looks like |
| --- | --- | --- | --- | --- |
| **Narrative fidelity** | 20 | No clear argument or decision path | Main story exists but has gaps or redundancy | The deck moves cleanly from context to recommendation and ask |
| **Action-title clarity** | 15 | Titles are topics, not takeaways | Some titles carry claims, some stay generic | Titles alone reveal the argument in skim mode |
| **Slide-role discipline** | 10 | Slides blur together with no distinct jobs | Most slide roles are visible | Each slide has a crisp role and the sequence feels intentional |
| **Evidence quality** | 10 | Claims float without proof | Basic proof exists but hierarchy is thin | Evidence supports the argument with clear emphasis and appendix discipline |
| **Writing quality** | 10 | Copy is inflated, vague, or repetitive | Mostly clear with some drag | Copy is crisp, specific, and easy to say aloud |
| **Design-system consistency** | 10 | Layout, type, or chart treatment drift heavily | Mostly consistent with minor noise | The deck feels governed by a chosen visual system |
| **Readability and accessibility** | 10 | Dense, low-contrast, or hard to follow | Legible in common cases | Clear hierarchy, contrast, pacing, and reading order feel deliberate |
| **Editability and maintenance** | 10 | Meaningful content is trapped in images or brittle overrides | Deck is editable but uneven | Text, charts, layouts, and theme choices are maintainable and safe to update |
| **Update resilience** | 5 | Any content change would break the story or deck structure | Some updates are possible with care | The deck can absorb likely updates without collapsing |

### Score bands

| Score | Meaning |
| --- | --- |
| **0-59** | Fail. The upstream brief, story, or generation setup needs rework. |
| **60-74** | Weak draft. Useful for discussion, not ready for reuse or delivery. |
| **75-84** | Good working deck. Worth refining and testing. |
| **85-100** | Strong candidate for packaging or real presentation use. |

### Hard fail gates

Fail the deck regardless of score if any of these are true:

- no clear decision or takeaway path exists
- titles do not work in skim mode
- important proof is missing where the recommendation depends on it
- the deck is image-heavy in ways that block normal editing
- layout or readability breaks the presenter or audience experience

### Validation layers

Run evaluation in this order:

1. brief and narrative match check
2. slide-title skim test
3. rendered deck review
4. PPTX editability and structure review
5. score with this rubric
6. diagnose using the failure library

For high-stakes decks, do not promote the work without human review.

## Part 2: Failure-mode library

### How to use it

Do not treat failure modes as slide bugs only.

Each one points to a weak upstream input.

Fix the deck brief, narrative artifact, vocabulary package, slide contract, or PPTX workflow before the next run.

| Failure mode | Signature | Likely cause | Upstream fix |
| --- | --- | --- | --- |
| **Topic-title drift** | Titles name subjects instead of claims | Narrative thesis was weak or missing | Require action-title discipline and a controlling idea |
| **Bullet sludge** | Slide copy sounds polished but says little | Writing rules were weak and slide role unclear | Tighten writing guidance and shrink the slide job |
| **Three-box reflex** | Many slides collapse into equal-width boxes | Model fell back to common template priors | Ban three-peer layouts by default and specify slide structure |
| **Agenda filler** | Agenda or section slides add length without value | Generic deck pattern was copied blindly | Require each slide to justify its role in the argument |
| **Appendix leakage** | Main story contains backup detail that should be separate | No main-story versus appendix discipline | Add appendix rules and cut candidates before build |
| **Chart theater** | Charts exist but do not carry a takeaway | Proof hierarchy was not defined | Require chart takeaway statements and evidence priorities |
| **Icon-row cliche** | Icons decorate without clarifying meaning | Visual polish substituted for argument | Ban icon filler and require information purpose |
| **Generic corporate mood** | The deck looks pleasant but has no point of view | Presentation vocabulary was too open | Define thesis, archetype, and banned patterns |
| **Screenshot lock-in** | Meaningful text or charts are baked into images | Generation optimized for visual appearance only | Require editable object standards and PPTX verification |
| **Masterless drift** | Slide formatting diverges over time | Theme and layout system were not controlled | Tighten master-slide and layout strategy |
| **Overlong deck** | The deck expands instead of compressing | AI defaulted to additive safety | Force cut candidates and slide-count pressure earlier |
| **Update breakage** | New numbers or changed audience break the story | No structured deck model for future edits | Preserve slide roles, evidence map, and update paths |

### Recurring diagnosis rule

If the same failure mode appears twice, it is not a one-off deck problem.

It is a system problem.

Promote the fix into:

- the brief template
- the narrative artifact
- the presentation vocabulary package
- the slide contract template
- the evaluation rubric

The workspace compounds only when the fix moves upstream.
