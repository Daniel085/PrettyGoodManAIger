# Setup & Architecture

How the whole thing fits together, and how to install it. For the 30-second pitch see the
[README](README.md); for the *why* behind the design see [docs/PRINCIPLES.md](docs/PRINCIPLES.md).

---

## ⚠️ The one rule: public package ≠ your working copy

There are two separate things. Do not mix them.

- **This repo (the public package)** holds templates, skills, prompts, playbooks, docs, and *fictional*
  examples. **It must never contain your real data.**
- **Your working copy** (default `~/pgmanaiger-working/`, a sibling folder *outside* this repo) holds
  your real memory, dossiers, decisions, and daily notes. **It is never committed anywhere.**

`/onboard` sets up the working copy for you in a separate location. (This rule is important enough that
it's stated again at the bottom — see "Keep your working copy out of the public repo.")

---

## Install

1. **Clone the package:**
   ```bash
   git clone https://github.com/Daniel085/PrettyGoodManAIger.git
   cd PrettyGoodManAIger
   ```
2. **Skills are auto-discovered.** Claude Code / Cowork picks up `.claude/skills/` automatically — no
   install step, no zipping. A skill named `start` gives you `/start`, and so on. (There is no `.skill`
   file format; skills are plain directories with a `SKILL.md`.)
3. **Run `/onboard`.** It interviews you, creates your working copy, seeds memory + your boss dossier,
   helps you schedule the rituals, and runs your first `/start` so you see it work.

That's it. From there you live in the rituals.

---

## The architecture

```
PrettyGoodManAIger/                  ← public package (this repo) — no real data
├── README.md  SETUP.md  LICENSE
├── START-HERE.md                    ← "Run START-HERE.md" onboarding pointer
├── .claude/skills/                  ← the slash-command runtime (Claude Code / Cowork)
│   ├── onboard, start, sync, wrap-up        (daily rituals — the heartbeat)
│   ├── prep-1on1, prep-boss-1on1            (managing down / up)
│   ├── capture-decision, reflect-on-decisions
│   └── weekly-digest
├── prompts/                         ← same logic as skills, as plain prompts (model-agnostic, P6)
├── templates/                       ← schemas copied into your working copy
├── playbooks/                       ← reusable management plays (seeded + your own)
├── examples/                        ← fictional worked dossiers (safe to ship)
├── docs/                            ← PRINCIPLES, REFERENCES, PRIVACY, INSTALL
└── people/ boss/ decisions/         ← EMPTY skeleton (READMEs only); real data is gitignored

~/pgmanaiger-working/                ← your private install (separate, never committed)
├── assistant-config.md  Memory/memory.md
├── Task Board.md  Scratchpad.md  Accomplishments.md
├── Daily Notes/  Meetings/
└── people/  boss/  decisions/        ← your real, private dossiers and decisions
```

## How the rituals chain together

- **`/onboard`** (once) → seeds memory + boss dossier, schedules the rituals, runs the first `/start`.
- **`/start`** (morning) → reads memory, briefs you, captures intentions, offers 1:1 prep.
- **`/sync`** (mid-day) → clears scratchpad + meeting notes; proposes dossier updates (you approve).
- **`/wrap-up`** (evening) → updates memory + accomplishments; offers to log a decision.
- **On demand:** `/prep-1on1`, `/prep-boss-1on1` before meetings; `/capture-decision` after a hard call.
- **Weekly:** `/weekly-digest` — the Leadership Weather Report across everything.
- **Quarterly:** `/reflect-on-decisions` — grade your judgment, mine your own playbooks.

Three feedback loops close: **managing down** (prep reads what capture wrote), **managing up** (boss
prep reads the profile, refined after meetings), and **reflection** (decisions logged before the
outcome, graded later). See [PRINCIPLES.md](docs/PRINCIPLES.md), P7.

## What `/onboard` does

Interviews you (role, manager, stakeholders, tools, timezone, your shorthand), builds the
name-canonicalization map, seeds `Memory/memory.md` and one boss dossier, walks you through scheduling
the three rituals (Claude Code Routines — 1-hour minimum, cloud-run), and runs your first `/start`.
Full detail in `.claude/skills/onboard/SKILL.md`.

## The privacy story

Real coworker notes are sensitive. They live in your working copy, outside this repo, never committed.
Keep proprietary/confidential data out of the AI entirely, and check your employer's policy before
seeding real people. Full detail — including the `git rm --cached` recovery move — in
[docs/PRIVACY.md](docs/PRIVACY.md).

---

## Keep your working copy out of the public repo

Stated once at the top, restated here because it's the one mistake that matters: **your working copy
lives outside this repo and is never committed.** If you ever run rituals inside the repo instead of a
separate folder, the `.gitignore` ignores the live files as a backstop — but a separate
`~/pgmanaiger-working/` is safer and is what `/onboard` sets up. Verify with `git check-ignore` before
your first commit, and use `git rm --cached` if something private ever slips in.
