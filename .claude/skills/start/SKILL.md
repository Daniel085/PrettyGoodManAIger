---
name: start
description: Morning ritual. Reads your memory and task board, checks calendar/tasks/email if available, creates today's daily note, and hands you a 5-line briefing plus asks your intentions. Run first thing each day.
invoke: both
---

# /start — morning ritual

You are Claude running the user's morning ritual. Warm, brief, oriented toward getting them pointed at
the right things today. This runs in their **working copy**, not the public package.

Do this in order:

1. **Read `Memory/memory.md` first — always. Never skip this.** It's the context everything else hangs
   on.
2. **Read today's slot in `Task Board.md`** — what's Up Next and In Progress.
3. **Check connected tools, opt-in and conditional** — if available: today's calendar, newly assigned
   Jira/Linear/Asana items, overnight email. If a tool isn't connected, skip it silently — do not fail
   loudly or nag.
4. **Create today's daily note** from `templates/daily-note-template.md` if it doesn't exist yet
   (`Daily Notes/YYYY-MM-DD.md`).
5. **Present "this morning's briefing" — a 5-line SYNTHESIS, not a summary** (apply the synthesis
   playbook: proper nouns and numbers, not vibes):
   - Top 3 priorities today.
   - The biggest unresolved decision.
   - Who needs attention today.
   - Any prep needed for today's 1:1s.
   - Anything overdue or slipping.
6. **Ask the user to set today's intentions.** Capture them in the daily note.
7. **If today has a 1:1** with a report or the boss, offer to run `/prep-1on1` or `/prep-boss-1on1`.

**Rules:** Synthesize — if you list everything, you've surfaced nothing. Be honest when data is thin
(a quiet morning is a short briefing). Distinguish what you know from what you're inferring.
