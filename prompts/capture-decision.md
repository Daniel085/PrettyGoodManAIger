# Prompt: Capture a Decision

**When:** right after you make a meaningful judgment call — a prioritization, a people call, an
escalation, a bet. Goal: log it in ~60 seconds, BEFORE you know how it turns out. That timing is the
whole value: honest reasoning, recorded before hindsight rewrites it.

**What counts:** non-trivial calls where you could reasonably have gone the other way, and where
you'd learn something from being right or wrong. Skip routine/obvious decisions — log the ones your
future self would want to grade.

**How to run:** answer the four questions below (talk or type — fragments are fine). The AI drafts a
decision file from `templates/decision-template.md` for you to approve. Can also be invoked by
`capture-post-1on1.md`, which already flags decisions made in a 1:1.

---

## Instructions to the AI

Turn my answers into a decision file using `templates/decision-template.md`. Keep my reasoning in my
words — don't sand off the nuance or make it sound more confident than I am.

**Ask me (or read from what I paste):**
1. **What did you decide, and what was the situation?** (context + decision)
2. **Why — what's your actual reasoning?** (what you're weighting, what you're discounting)
3. **What do you expect to happen if you're right?** (make it concrete/checkable)
4. **How confident are you, and when should we revisit?** (high/med/low + a revisit date)

**Then:**
- Draft the file. Propose a `revisit` date (default ~3 months, or sooner if I gave one).
- Suggest `people:` links to any reports/bosses involved (e.g. `[[daniel]]`).
- Set `status: open`. Leave the **Outcome** section empty — never pre-fill it.
- Propose a filename: `decisions/YYYY-MM-DD-<slug>.md`.

**Rules:**
- Capture must be fast — if I'm terse, draft from what I gave and flag what's thin. Don't interrogate.
- Record confidence honestly. Don't inflate it; the whole point is to grade calibration later.
- This is a snapshot in time. Once saved, the top half is frozen — only the Outcome gets filled in
  at revisit.

---

## My answers
```
<answer the 4 questions here, or paste raw — e.g. "decided X because Y, expect Z, ~70% confident,
check in Sept">
```
