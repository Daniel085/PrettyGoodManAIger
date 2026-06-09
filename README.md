# Pretty Good Man-AI-ger

**A personal AI assistant for product managers — a daily-ritual architecture loaded with the manage-up
canon and a decision log.**

It's not an app. It's a set of **daily rituals** (`/start`, `/sync`, `/wrap-up`), **structured files**,
and **management playbooks** that run inside Claude Code / Cowork — so the assistant remembers what you
can't, and gets sharper the longer you use it.

> The promise: instead of generic "how to manage" advice, you get advice grounded in *your* people,
> *your* boss, and *your* decisions — and it compounds, because the daily rituals feed it whether or
> not you remember to.

> 🚀 **First time here?** Clone this, open it in Cowork / Claude Code, and run **`/onboard`** (or say
> "Run START-HERE.md"). You'll get a 1-minute overview, a seeded setup, and your first `/start`. Full
> install + data-safety: [SETUP.md](SETUP.md) · [docs/PRIVACY.md](docs/PRIVACY.md).

**The wedge:** there are generic personal-assistant kits, and there are management books. Few fuse the
two for a specific role. This one does — Crist-style daily-ritual *mechanism* carrying the manage-up
*curriculum* (Gabarro & Kotter, Cohen & Bradford, Neffinger & Kohut, Annie Duke). Tuned for **Product &
Design managers of individual contributors**. Lineage and citations:
[docs/PRINCIPLES.md](docs/PRINCIPLES.md) · [docs/REFERENCES.md](docs/REFERENCES.md).

---

## Why this exists

Management context decays. Six weeks after a great 1:1 you've forgotten what you committed to, what
your report is worried about, and why you made the call you made. So you wing it — and your AI, with
no memory of any of it, gives you advice as generic as a search result.

This system fixes that by maintaining living, private files and pairing them with prompts that read
and update them. The core design bet:

> **Capture must be cheaper than the value it returns — and it has to actually happen.**
> Cheap capture isn't enough; something has to *trigger* it. So capture is tied to **scheduled daily
> rituals**, not willpower. `/start`, `/sync`, `/wrap-up` fire morning/mid-day/evening and feed the
> system whether or not you remembered. That's the difference between a living assistant and a folder
> of files you stop opening in week three.

---

## The daily rhythm (the heartbeat)

Three scheduled rituals carry everything else. Set them up once with `/onboard`; they run morning,
mid-day, and evening.

```
/start    morning  →  reads memory, briefs you, captures intentions, offers 1:1 prep
/sync     mid-day  →  clears scratchpad + meeting notes, proposes dossier updates (you approve)
/wrap-up  evening  →  reflects, updates memory + accomplishments, offers to log a decision
```

This is the *mechanism*. The loops below are the *substance* the rituals carry.

---

## The loops (the substance)

The system has two halves, because you manage in two directions — plus a reflection loop and a weekly
synthesis that sit on top.

### Managing down — your reports
```
prep-1on1  →  have the 1:1  →  capture-post-1on1  →  (dossier gets richer)  →  better prep next time
```

### Managing up — your boss, skip-level, stakeholders
```
build-boss-profile  →  prep-boss-1on1  →  have the meeting  →  refine the profile  →  sharper next time
```

### Reflecting — your own judgment
```
capture-decision (before outcome)  →  ... time passes ...  →  reflect-on-decisions (grade + find patterns)
```

Each loop **compounds**: the output of one conversation becomes input that makes the next one better.
That feedback loop is the whole point — it's what "gets smarter as you lead" actually means.

### Synthesizing — the weekly step-back
Once a week, `weekly-digest.md` reads across *all* of the above and gives you one **Leadership Weather
Report**: the overall read, who needs attention, decisions due for revisit, blind-spot patterns, and a
ruthless top-3 for the week ahead. It's where the firefighting stops and you see the whole field.

---

## What's in the box

```
.claude/skills/   The slash-command runtime (Claude Code / Cowork) — auto-discovered
  onboard, start, sync, wrap-up     daily rituals (the heartbeat)
  prep-1on1, prep-boss-1on1         managing down / up
  capture-decision, reflect-on-decisions
  weekly-digest

templates/        Schemas copied into your working copy
  memory, assistant-config, task-board, scratchpad, accomplishments,
  daily-note, meeting-note         the productivity backbone
  person-dossier, boss-dossier, decision, playbook   the management schemas

playbooks/        Reusable management plays (seeded frameworks + your own, over time)
  synthesis-30-second-update · scqa-and-pyramid · advice-not-feedback ·
  one-on-one-as-decision-room

prompts/          Same logic as the skills, as plain prompts (model-agnostic — P6)
  capture-post-1on1 · prep-1on1 · build-boss-profile · prep-boss-1on1 ·
  capture-decision · reflect-on-decisions · weekly-digest · extract-playbooks

examples/         Fictional worked dossiers (Alex Chen PM, Sam Rivera Director, a decision)
docs/             PRINCIPLES · REFERENCES · PRIVACY · INSTALL
people/ boss/ decisions/   Empty skeleton — your real data is gitignored, lives in your working copy
```

Your **real data lives in a separate working copy** (`~/pgmanaiger-working/`), never in this repo. See
[SETUP.md](SETUP.md) for the architecture and [docs/PRIVACY.md](docs/PRIVACY.md) for why.

---

## How to use it (Claude Code / Cowork)

> **Installing?** See **[SETUP.md](SETUP.md)** (architecture + install) and
> **[docs/PRIVACY.md](docs/PRIVACY.md)** (data-safety + employer-policy — important; this kit holds
> private notes about real coworkers).

1. **Onboard once.** Clone, open in Cowork, run **`/onboard`**. It interviews you, seeds your working
   copy (memory + your boss dossier), helps you schedule the rituals, and runs your first `/start`.
2. **Live in the rituals.** `/start` each morning, `/sync` after lunch, `/wrap-up` at end of day. They
   keep capture cheap and current — this is what keeps the system alive.
3. **Prep & capture around meetings.** `/prep-1on1` or `/prep-boss-1on1` before; your meeting notes get
   swept in at the next `/sync`. Log hard calls with `/capture-decision`.
4. **Step back.** `/weekly-digest` once a week; `/reflect-on-decisions` quarterly to grade your judgment
   and mine your own playbooks.

Not on Claude Code? Every skill has a plain-prompt twin in `prompts/` you can paste into any LLM (P6).

### A note on data & privacy
These dossiers are **private manager's notes** — candid coaching judgments by design, for you, not for
sharing with the people described. Keep **proprietary, customer, or confidential** material out of the
AI unless your company has blessed it, and **check your employer's policy** before seeding real people.
Your working copy lives outside this repo and is never committed. Full detail:
[docs/PRIVACY.md](docs/PRIVACY.md).

---

## Design principles (the short version)

The architecture is deliberate. Each choice traces to a principle — full rationale and citations in
**[docs/PRINCIPLES.md](docs/PRINCIPLES.md)**:

- **Capture cheaper than value, triggered by ritual** — cheap capture isn't enough; scheduled daily
  rituals make it *happen*, instead of relying on willpower. This is the survival mechanism.
- **Data before payoff** — a prep prompt on an empty dossier is just generic AI. Seed first.
- **Observed vs. inferred, always separated** — never let a guess harden into a fact.
- **Append-only history; approve, don't overwrite** — the dossier is auditable and you stay the editor.
- **Specialize over generalize** — a kit that knows Product/Design management beats one that serves
  everyone blandly. Specificity is the entire value proposition.
- **Manage in two directions** — down (develop people) and up (mutual dependence, not flattery).
- **Compounding is the product** — the feedback loop, not the file, is what makes this an assistant
  that gets smarter, rather than a static notes folder.
- **Judge decisions by quality, not outcome** — log calls before the result is in, revisit to
  calibrate your judgment honestly. This is the engine that helps *you* get better, not just organized.

---

## Credits & lineage

Built on ideas from a public talk by Dave Kline & Marsden on building a "management second brain," the foundational
management-up literature (Gabarro & Kotter; Cohen & Bradford; Neffinger & Kohut), and the file
mechanics of the open-source [COG-second-brain](https://github.com/huytieu/COG-second-brain) (MIT).
Full attributions in [docs/REFERENCES.md](docs/REFERENCES.md).
