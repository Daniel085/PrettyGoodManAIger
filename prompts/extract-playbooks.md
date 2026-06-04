# Prompt: Extract My Playbooks (the compounding capstone)

**When:** periodically, once you have real history — a meaningful number of logged decisions, 1:1
captures, and a reflection pass or two. This is what turns a *generic* assistant into *yours*: it
watches how you actually manage and codifies your repeated, working moves into playbooks in your own
voice. (Also runs as a sub-step of `reflect-on-decisions.md` pattern review.)

**Honest prerequisite:** this needs data to mine. With only a handful of entries it will (correctly)
tell you it's too early and decline to invent plays. Don't force it — premature extraction produces
generic advice dressed up as personal insight, which is exactly what this whole system exists to
avoid.

**How to run:** point it at `decisions/`, `people/` (Timelines + Coaching Notes), and any reflection
output. It proposes new playbook files using `templates/playbook-template.md`.

---

## Instructions to the AI

Mine my actual management history for repeated, evidence-backed patterns and propose playbooks that
capture *how I work* — not best practices in general. The test for every proposed play: **could you
point to the specific entries where I did this, and where it worked?**

**Look across:**
- `decisions/` — recurring kinds of calls I make, and (from Outcome sections) which of my moves
  reliably work out. A move that's paid off 3+ times is a candidate.
- `people/` Coaching Notes and Timelines — coaching moves/reframes I reuse across reports.
- Reflection output — strengths and calibration patterns already surfaced.

**For each candidate pattern, propose a playbook** using `templates/playbook-template.md`:
- Name it for the move, in my voice.
- **When to use** — the trigger I actually respond to.
- **How** — the shape of the move as I do it.
- **Why it works (for me)** — with **specific evidence**: cite the decisions/1:1s that show it.
- **Guardrail** — when it didn't work or shouldn't apply (look for counter-examples in my history;
  if a "win" pattern also has failures, that IS the guardrail).
- Set `Source: extracted from my own practice`, a `Confidence` level, and the instance count.

**Rules — these matter most:**
- **Evidence or it doesn't ship.** No playbook without specific cited instances. If you can't point
  to where I did it, don't propose it.
- **Threshold honestly.** Name the minimum bar (e.g. ~3 instances). If a pattern is real but thin,
  propose it as a *tentative* play at `confidence: low` and say what would confirm it.
- **Too-early is a valid answer.** If the history can't support real extraction yet, say so plainly,
  tell me roughly how much more data would help, and stop. Do not pad.
- **Don't restate the seeded playbooks.** I already have the general frameworks; surface what's
  distinctive to ME — including where my actual practice *diverges* from the seeded advice.
- These are proposals. I approve before any file is written to `playbooks/`.

End with: which 1–2 proposed plays are best-supported, and what pattern is *almost* there but needs
more data before it's a play.

---

## Context
- Mine from: `decisions/`, `people/`, reflection output
- Minimum instance bar: `<default ~3; adjust if I say>`
