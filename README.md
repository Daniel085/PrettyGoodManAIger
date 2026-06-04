# Management Assistant

A personal AI system that makes you a better manager by remembering what you can't — and that
*compounds the longer you use it*. It is not an app. It is a small set of **structured files**,
**reusable prompts**, and **playbooks** that you run inside Claude / Cowork (or any capable LLM).

> The promise: instead of generic "how to manage" advice, you get advice grounded in *your* people,
> *your* boss, and *your* decisions — and it gets sharper every week, because every 1:1 and every
> meeting feeds it.

This kit is tuned for **Product & Design managers of individual contributors** — though the structure
generalizes. It is a polished, shareable take on the "management second brain" idea Dave Kline &
Marsden (MGMT Accelerator) described in a public talk — reframed here as a practical *assistant* — and
grounded in the classic management literature on managing up
(see [docs/PRINCIPLES.md](docs/PRINCIPLES.md) and [docs/REFERENCES.md](docs/REFERENCES.md)).

---

## Why this exists

Management context decays. Six weeks after a great 1:1 you've forgotten what you committed to, what
your report is worried about, and why you made the call you made. So you wing it — and your AI, with
no memory of any of it, gives you advice as generic as a search result.

This system fixes that by maintaining living, private files and pairing them with prompts that read
and update them. The core design bet:

> **Capture must be cheaper than the value it returns — every single time.**
> A system that depends on a heroic weekly ritual dies in three weeks. One that captures in 90
> seconds and pays you back at the next meeting survives.

---

## The two loops

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
templates/   Reusable schemas — the shape of a "dossier" / a decision
  person-dossier-template.md     A direct report (managing down)
  boss-dossier-template.md       A boss / skip-level / stakeholder (managing up)
  decision-template.md           A single judgment call, logged before the outcome

people/      One file per direct report (e.g. daniel.md)
boss/        One file per boss / skip / key stakeholder
decisions/   One file per meaningful judgment call (YYYY-MM-DD-slug.md)

playbooks/   Reusable plays — frameworks + (eventually) your own codified moves
  synthesis-30-second-update.md  The "How's the project?" answer
  scqa-and-pyramid.md            Structure thinking, then deliver it
  advice-not-feedback.md         Pull your boss in as a co-owner
  one-on-one-as-decision-room.md Turn status meetings into decision meetings

prompts/     Reusable prompts you run against the files above
  capture-post-1on1.md   raw notes → proposed dossier edits      (down: capture)
  prep-1on1.md           report dossier → 60-second brief        (down: payoff)
  build-boss-profile.md  email/Slack → boss dossier              (up: capture)
  prep-boss-1on1.md      boss dossier → decision-room brief       (up: payoff)
  capture-decision.md    a judgment call → frozen decision file  (reflect: capture)
  reflect-on-decisions.md decisions → graded verdicts + patterns  (reflect: payoff)
  weekly-digest.md       everything → Leadership Weather Report   (weekly synthesis)

docs/        This documentation + the architectural principles and citations
```

---

## How to use it (Claude / Cowork)

1. **Seed a dossier.** For a report, copy `templates/person-dossier-template.md` to `people/<name>.md`
   and fill it (or have Claude interview you). For a boss, run `prompts/build-boss-profile.md` — it
   pulls from your **Gmail and Slack connectors** by default, with paste as a fallback.
2. **Prep before meetings.** Run `prep-1on1.md` (reports) or `prep-boss-1on1.md` (boss) against the
   dossier. Read the 60-second brief. Optionally schedule it to run overnight.
3. **Capture after meetings.** Paste your raw notes into `capture-post-1on1.md`. It proposes edits —
   you approve them. ~90 seconds. This is the step that keeps the brain alive; protect it.
4. **Grow your playbooks.** Drop in frameworks you like (EOS, OKRs, a coaching format). Over time the
   system can codify *your* repeated moves into playbooks of your own.

### A note on data & privacy
These dossiers are **private manager's notes** — candid coaching judgments included by design. They
are for you, not for sharing with the people described. And following the guidance in the source talk: keep
**proprietary, customer, or confidential** material out of the AI unless your company has explicitly
blessed it. Tone, format, decision style, and your own observations are fine; secrets are not.

---

## Design principles (the short version)

The architecture is deliberate. Each choice traces to a principle — full rationale and citations in
**[docs/PRINCIPLES.md](docs/PRINCIPLES.md)**:

- **Capture cheaper than value** — or the system dies. Every design choice bends toward cheap capture.
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
