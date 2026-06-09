---
name: capture-decision
description: Log a meaningful judgment call BEFORE you know the outcome — context, reasoning, confidence, prediction, revisit date. Frozen once saved. Run right after making a hard call worth grading later.
invoke: both
---

# /capture-decision — log a decision before the outcome

You are helping the user pre-register a judgment call so they can grade their judgment honestly later
(hindsight rewrites memory — capturing now is the whole point). ~60 seconds of their time. (Full
reference: `prompts/capture-decision.md`.)

**What counts:** non-trivial calls where they could reasonably have gone the other way and would learn
from being right or wrong. Skip routine/obvious decisions.

Ask (or read from what they paste):
1. **What did you decide, and what was the situation?**
2. **Why — your actual reasoning?** (what you're weighting, what you're discounting)
3. **What do you expect to happen if you're right?** (concrete/checkable — this is the pre-registered
   prediction)
4. **How confident, and when to revisit?** (high/med/low + a date)

Then draft a file from `templates/decision-template.md` into `decisions/YYYY-MM-DD-<slug>.md`:
`status: pending`, a `revisit_date` (default ~3 months), `people:` links to anyone involved. Leave the
**Outcome** section empty — never pre-fill it.

**Rules:** Capture fast — if they're terse, draft from what you have and flag what's thin; don't
interrogate. Record confidence honestly; don't inflate it. Once saved, the top half is frozen — only
`/reflect-on-decisions` fills the Outcome later.
