---
name: verify
description: >
  Generate a verification evidence pack for work that was just built. The agent captures
  evidence (screenshots, video, GIF, structured output) based on task type, reviews its own
  output, fixes issues it catches, and packages everything into an HTML report. The human
  reviews the report and adds feedback. Use after building (TDD or any substantial work session)
  when you want proof that what was built actually works. Slash-command only — `/verify`.
  Does NOT replace QA or testing — it produces reviewable evidence of the current state.
disable-model-invocation: true
---

# Verify — "Prove it works"

Generate an evaluation pack for whatever was just built. The agent captures evidence, reviews its own output, iterates if needed, then packages a single HTML report for the human.

This is a verification-first skill. The goal is to make the agent produce evidence that is fast for a human to review — and to force the agent to exercise the real system instead of only describing it.

## When to use this skill

After building. The code is written, tests pass, the feature exists. Now you want proof.

```
BUILD:      ... → to-issues → tdd → ship
VERIFY:                                    /verify → (human reviews) → /postmortem
FEEDBACK:                                                      /qa → (back to grill-me)
```

This skill does NOT:
- Replace tests (that's `tdd`)
- Capture bugs conversationally (that's `qa`)
- Compound learnings into instructions (that's `postmortem`)

## Step 1: Determine task type and evidence format

Identify what kind of work was just done. Pick the evidence format:

| Task kind | Evidence | How to capture |
|---|---|---|
| UI interactive flow | Video + key screenshots | Browser recording, screenshot at each state change |
| UI sequential actions | GIF of action sequence + screenshots | Browser automation, capture frames |
| UI static | Screenshots at key states | Browser screenshot |
| API / backend | Structured test output + fixture captures | Run test suite, capture request/response pairs |
| CLI / terminal | Animated GIF of terminal session | Record terminal with `asciinema` or screenshot sequence |
| Docs | Rendered diff summary | `git diff` of changed docs, formatted |
| Data / config | Before/after comparison table | Structured output of state changes |

If the issue slice has a "How to verify" field (from `to-issues`), read it and follow the specified review method. If not, choose based on the table above.

Ask the user to confirm: *"I'll capture [evidence type] for this [task kind] work. Sound right?"*

## Step 2: Generate evidence

Capture the evidence using the appropriate method.

### For UI work

1. Start the dev server or open the running application
2. Navigate to the feature
3. Capture screenshots at each meaningful state
4. For interactive flows: record a video
5. For sequential actions: capture frames and assemble a GIF

### For non-UI work

1. Run the relevant test suite — capture full output
2. Run any fixtures or stress tests
3. Capture before/after state where applicable

## Step 3: Self-review

**This is the critical step.** The agent examines its own evidence before handing it to the human.

For screenshots and visual media:
- Read back each screenshot using image analysis
- Check: does the UI render correctly? Are there layout issues, missing content, broken states?
- Check: does the visual match what the issue/PRD described?

For structured output:
- Read through the test output, fixture captures, or diffs
- Check: do the results match expectations? Are there failing tests, warnings, or anomalies?

If you find issues:
1. Note them
2. Fix the underlying problem
3. Regenerate evidence
4. Self-review again

Repeat until the evidence looks clean or you've identified issues that need human decision.

## Step 4: Package the HTML report

Build a single HTML report in `proofs/<YYYY-MM-DD>-<slug>/`. The folder name uses today's date and a short slug describing what was verified.

The HTML report must include:

1. **Summary** — what was built, what was verified, pass/fail assessment
2. **Evidence** — embedded screenshots, embedded or linked video/GIF, structured output
3. **Self-review findings** — what the agent caught during self-review, what was fixed, what remains
4. **Open questions** — anything the agent is uncertain about that needs human eyes
5. **Recommendations** — suggestions for improvement (not fixes, those are done; this is "could be better")

The report should be navigable. Use section headers. Link to full-size images if thumbnails are used. The goal is that a human can review in under 5 minutes.

## Step 5: Present to the human

Share the report location and give a brief verbal summary:

- *"The evaluation pack is at `proofs/2026-04-19-<slug>/report.html`"*
- *"Summary: [X] things verified, [Y] issues found and fixed, [Z] open questions."*
- *"Key findings: [1-2 sentence highlight of what matters most]"*

Then ask: *"What do you think? Anything catch your eye?"*

Wait for human feedback. If the human finds issues:
- Note them for the postmortem
- Fix what you can
- Regenerate evidence if needed

## Step 6: Save final state

After human review is done (or the human moves on):
- Ensure the HTML report reflects the final state
- Note the human's feedback in the conversation context (for `/postmortem` to pick up)
- Update `work/current.md` if needed

## Rules

- **Evidence type matches task type** — don't take screenshots of an API, don't write structured output for a UI flow.
- **Self-review before human review** — the agent always looks at its own output first. The human should not catch things the agent could have caught.
- **Fix what you find** — if self-review reveals issues, fix them and regenerate. Don't hand the human known-broken output.
- **HTML is the standard format** — terminal output is hard to scan at scale. One HTML file, navigable, with all evidence embedded or linked.
- **The evaluation pack is a snapshot** — it proves the state at a point in time. It is not a living document.
- **Don't over-capture** — evidence should be sufficient for review, not exhaustive. A 30-second video beats a 5-minute one. 5 screenshots beat 50.
