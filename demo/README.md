# demo/ — a pre-seeded fictional working copy

**Kick the tires in five minutes, zero setup, zero real data.** This folder is what a working copy
looks like after a few weeks of real use — except everyone in it is fictional. You play **Jordan
Park**, a Group PM at Northbeam (a fictional B2B SaaS company), who manages **Alex Chen** (Senior PM)
and **Priya Desai** (Product Designer), and reports to **Sam Rivera** (Director of Product).

The state is set to **Monday evening, June 8, 2026**: there's an unprocessed scratchpad, a fresh
meeting note from today's eng sync, a decision past its revisit date, and a 1:1 with Alex on
tomorrow's calendar. In other words — the rituals have work to do.

## Try it

Tell Claude to run any skill **against this folder as the working copy**:

> "Run `/start` using `demo/` as the working copy."

Good tour, in order:
1. **`/start`** — the morning briefing (it should surface the Alex 1:1, the slipping Marco retro, and
   the decision due for revisit).
2. **`/prep-1on1` for Alex** — a rich brief from a full dossier.
3. **`/prep-1on1` for Priya** — see how it behaves when the dossier is *thin* (it should say so, not pad).
4. **`/sync`** — watch it propose dossier updates from the scratchpad + meeting note, as diffs.
5. **`/weekly-digest`** — the Leadership Weather Report across everything.

## Reset when done

Playing with the demo mutates it (that's the point). Restore the pristine state any time:

```bash
git checkout -- demo/
```

> Everything in this folder is **fictional** and intentionally tracked in git (unlike your real
> working copy, which lives outside the repo and is never committed — see `../docs/PRIVACY.md`).
