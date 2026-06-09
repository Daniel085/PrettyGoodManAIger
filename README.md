# Pretty Good Man-AI-ger

**A personal AI assistant for product managers — a daily-ritual architecture loaded with the manage-up
canon and a decision log.**

Not an app. A set of **daily rituals** (`/start`, `/sync`, `/wrap-up`), **structured files**, and
**management playbooks** that run inside Claude Code / Cowork — so the assistant remembers what you
can't, and gets sharper the longer you use it.

> Instead of generic "how to manage" advice, you get advice grounded in *your* people, *your* boss, and
> *your* decisions — and it compounds, because the daily rituals feed it whether or not you remember to.

Tuned for **Product & Design managers of individual contributors**. Built on a public talk by Dave Kline
& Marsden, the classic manage-up literature (Gabarro & Kotter; Cohen & Bradford; Neffinger & Kohut;
Annie Duke), and the file mechanics of [COG-second-brain](https://github.com/huytieu/COG-second-brain)
(MIT).

---

## Quickstart (Claude Code / Cowork)

```bash
git clone https://github.com/Daniel085/PrettyGoodManAIger.git
cd PrettyGoodManAIger
```
Open the folder in Cowork / Claude Code (skills auto-load), then run **`/onboard`**. It interviews you,
seeds a private working copy (memory + your boss dossier), helps you schedule the rituals, and runs your
first `/start`.

From there: `/start` each morning, `/sync` after lunch, `/wrap-up` at end of day — plus `/prep-1on1` and
`/prep-boss-1on1` before meetings. **Want to see it first?** Read [A Day in the Life](docs/WALKTHROUGH.md).

> ⚠️ This kit holds **candid notes about real coworkers.** Your real data lives in a separate working
> copy, never committed. Read [docs/PRIVACY.md](docs/PRIVACY.md) and **check your employer's policy**
> before seeding real people.

---

## Why it exists

Management context decays. Six weeks after a great 1:1 you've forgotten what you committed to, what your
report is worried about, and why you made the call you made. So you wing it — and your AI, with no memory
of any of it, gives advice as generic as a search result.

The core design bet:

> **Capture must be cheaper than the value it returns — and it has to actually happen.**
> Cheap capture isn't enough; something has to *trigger* it. So capture is tied to **scheduled daily
> rituals**, not willpower. That's the difference between a living assistant and a folder of files you
> stop opening in week three.

---

## How it works

**The heartbeat — three scheduled rituals carry everything else:**

```
/start    morning  →  reads memory, briefs you, captures intentions, offers 1:1 prep
/sync     mid-day  →  clears scratchpad + meeting notes, proposes dossier updates (you approve)
/wrap-up  evening  →  reflects, updates memory + accomplishments, offers to log a decision
```

**The substance — the rituals feed four compounding loops:**

| Loop | Capture → Payoff |
|------|------------------|
| **Managing down** (reports) | `capture` in `/sync` → `/prep-1on1` reads it back |
| **Managing up** (boss) | `/build-boss-profile` → `/prep-boss-1on1`, refreshed via `/sync` |
| **Reflecting** (judgment) | `/capture-decision` (before outcome) → `/reflect-on-decisions` (grade later) |
| **Synthesizing** (weekly) | everything → `/weekly-digest` Leadership Weather Report |

Each loop compounds: the output of one conversation becomes input that makes the next one better. That
feedback loop is what "gets smarter as you lead" actually means. Full detail in
[docs/SKILLS.md](docs/SKILLS.md).

---

## What's in the box

```
.claude/skills/   11 slash-command skills (auto-discovered) — see docs/SKILLS.md
templates/        schemas: memory, task-board, scratchpad, accomplishments, daily/meeting notes,
                  + person/boss/decision/playbook dossiers — copied into your working copy
playbooks/        reusable management plays (seeded frameworks + your own, over time)
prompts/          model-agnostic twins of the skills (paste into any LLM — P6)
examples/         fictional worked dossiers (Alex Chen PM, Sam Rivera Director, a decision)
docs/             the documentation (index below)
people/ boss/ decisions/   empty skeleton — your real data is gitignored, lives in your working copy
```

Your **real data lives in a separate working copy** (`~/pgmanaiger-working/`), never in this repo.

---

## Documentation

| Doc | What it covers |
|-----|----------------|
| [SETUP.md](SETUP.md) | Architecture, install, the public-package-vs-working-copy model |
| [docs/WALKTHROUGH.md](docs/WALKTHROUGH.md) | **A day in the life** — the rituals playing out, with sample output |
| [docs/SKILLS.md](docs/SKILLS.md) | Per-skill reference: what each reads, produces, and when to run it |
| [docs/FAQ.md](docs/FAQ.md) | Failure modes & troubleshooting — honest about where it bends |
| [docs/PRINCIPLES.md](docs/PRINCIPLES.md) | The *why* — system-design (P1–P7) and management (M1–M9) principles |
| [docs/REFERENCES.md](docs/REFERENCES.md) | Full bibliography and lineage |
| [docs/PRIVACY.md](docs/PRIVACY.md) | What to keep out, data location, employer-policy, recovery |
| [docs/INSTALL.md](docs/INSTALL.md) | Detailed install notes (Cowork + other surfaces) |

New and want the fast path: **[WALKTHROUGH](docs/WALKTHROUGH.md)** → run `/onboard`. Want the deep
understanding: **[PRINCIPLES](docs/PRINCIPLES.md)**.

---

## Design principles (the short version)

Each choice traces to a principle — full rationale and citations in
[docs/PRINCIPLES.md](docs/PRINCIPLES.md):

- **Capture cheaper than value, triggered by ritual** — scheduled rituals make capture *happen* instead
  of relying on willpower. The survival mechanism.
- **Data before payoff** — a prep prompt on an empty dossier is just generic AI. Seed first.
- **Observed vs. inferred, always separated** — never let a guess harden into a fact.
- **Append-only history; approve, don't overwrite** — the dossier is auditable; you stay the editor.
- **Specialize over generalize** — a kit that knows Product/Design management beats one that serves
  everyone blandly.
- **Manage in two directions** — down (develop people) and up (mutual dependence, not flattery).
- **Compounding is the product** — the feedback loop, not the file, is what makes it get smarter.
- **Judge decisions by quality, not outcome** — log calls before the result is in; calibrate honestly.

---

## Credits & lineage

Built on ideas from a public talk by Dave Kline & Marsden on a "management second brain" (no paid course
materials used), the foundational manage-up literature (Gabarro & Kotter; Cohen & Bradford; Neffinger &
Kohut; Annie Duke; Barbara Minto), the daily-ritual architecture lineage (Michael Crist), and the file
mechanics of [COG-second-brain](https://github.com/huytieu/COG-second-brain) (MIT). Full attributions in
[docs/REFERENCES.md](docs/REFERENCES.md). Licensed MIT.
