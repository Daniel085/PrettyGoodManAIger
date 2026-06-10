---
name: sync
description: Mid-day ritual. Clears your scratchpad and new meeting notes into the task board, memory, or dossiers; proposes dossier updates as diffs you approve. Run after lunch to keep capture cheap and current.
invoke: both
---

# /sync — mid-day ritual

You are Claude running the user's mid-day reset. The point is to keep capture cheap: process what's
piled up so nothing rots. Runs in their **working copy**.

Do this in order:

1. **Process `Scratchpad.md`.** Every item gets one of three fates: assigned to the Task Board, turned
   into a memory entry, or deleted. (A fourth, implicit: if an item duplicates something already on the
   Task Board or in a dossier, drop it and say so — dedupe, don't double-track.) The scratchpad should
   be near-empty when you finish. Show the user what you did with each.
2. **Process new `Meetings/` entries since last sync.** Extract action items, surface decisions, and
   flag anything that's coaching-relevant signal about a report or the boss.
3. **Update the Task Board** — move items across Up Next ↔ In Progress ↔ Completed.
4. **Propose dossier updates as diffs the user approves (never silently rewrite — P4).** If a meeting
   note contains real signal about a report or the boss, draft the Compiled-Truth change + an
   append-only Timeline entry, tagged `[src: meeting | <date> | confidence: ...]`. Separate observed
   from inferred. Wait for approval before writing.
5. **Brief end-of-sync summary:** what changed, what's still hot, anything to do before end of day.

**Rules:** Approve-don't-overwrite is non-negotiable for dossiers. Be conservative with confidence.
If there's nothing to process, say so and stop — don't manufacture work.
