# Prompt: Post-1:1 Capture

**When:** right after a 1:1 with a report. Goal: turn messy notes into dossier updates in <90 seconds
of your time. This is the keystone — if capture is cheap, the brain stays alive.

**How to run (Claude / Cowork):** open this file + the report's dossier (e.g. `people/<name>.md`),
paste your raw notes where shown, and run. Review the proposed diff, then approve.

---

## Instructions to the AI

You are maintaining a manager's PRIVATE coaching dossier on a direct report. I'll give you the
current dossier and my raw notes from a 1:1. Produce updates — do not rewrite the whole file.

**Extract and propose:**
1. **Commitments** (either direction) → add rows to the Commitments table with today's date and
   status `open`. Mark any prior commitments now fulfilled as `done`.
2. **Compiled Truth changes** — only where the notes give real new evidence. For each, show the
   OLD line and the NEW line. Tag every claim `[src: 1:1 | <today> | confidence: high|med|low]`.
   Be conservative: one conversation rarely justifies high confidence.
3. **Open Threads** — add new ones; check off any resolved.
4. **Growth-edge / craft signals** — for a PM/designer, watch for: discovery vs. delivery vs.
   strategy strength, stakeholder friction, exec presence, saying-no, data fluency, craft quality.
   File these under Growth Edge / Strengths / Stakeholder context as appropriate, flagged as
   hypothesis (`[src: inference]`) vs. observation (`[src: 1:1]`).
5. **Timeline entry** — one dated, factual append-only bullet summarizing the conversation.
6. **Decisions made** — if I made a meaningful judgment call in this 1:1, flag it and offer to log it
   via `capture-decision.md` (don't force it for routine calls).

**Rules:**
- Never overwrite history. Material changes to Compiled Truth keep the old claim in the Timeline.
- Separate **observed** from **inferred** — never harden a guess into a fact.
- If the notes are thin, say so and propose less. Don't invent.
- Output as an explicit list of edits (file + section + old→new) I can approve, then the final files.

---

## My raw notes
```
<paste here — bullets, fragments, whatever. Don't clean them up.>
```
