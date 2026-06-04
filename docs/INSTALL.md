# Install & Setup

How to get the Management Assistant onto your machine and running in Claude. The recommended setup is
**Claude Cowork with a local clone of the repo** — Cowork can read the folder directly, which is
exactly how the prompts are designed to work.

---

## ⚠️ Before you start — data sensitivity & employer policy

This kit's dossiers contain **candid, private notes about real coworkers** — performance reads, growth
edges, coaching judgments. Treat that data accordingly:

- **Check your employer's policy** on putting performance/personnel information into AI tools *before*
  you use this on a work account or work machine. Coaching observations are often fine; some
  organizations treat performance data as restricted. If in doubt, ask first.
- **Keep proprietary, customer, and confidential material out** unless your company has explicitly
  blessed it. Tone, format, decision style, and your own observations are fine; secrets are not.
- **Your real dossiers should never leave your machine.** The setup below uses `.gitignore` so your
  private notes are *not* pushed to the public GitHub repo. Verify that before your first commit.
- These are **your private notes** — not for sharing with the people described.

---

## Recommended: Claude Cowork + local clone

### 1. Clone the repo to your work laptop
```bash
git clone https://github.com/Daniel085/PrettyGoodManAIger.git
cd PrettyGoodManAIger
```

### 2. Open the folder in Cowork
Point Claude Cowork at the cloned folder so it can read and write files in it. Cowork now has direct
access to `templates/`, `prompts/`, `playbooks/`, and your `people/` `boss/` `decisions/` folders.

### 3. Confirm your private data is gitignored
The repo ships a `.gitignore` that keeps real dossiers out of version control while preserving the
templates and the example. Verify it's working **before** you create any real notes:
```bash
git status            # after creating people/marcus.md, it should NOT appear as a change
git check-ignore people/marcus.md   # should print the path = it's ignored = safe
```
Only `people/daniel.md` (a fictional example), the folder READMEs, and `.gitkeep` placeholders are
tracked. Everything else you create in those folders stays local.

### 4. Let it onboard you
The simplest start: tell Cowork **"Run START-HERE.md."** It gives a 1-minute overview, checks your
setup, and walks you to your first action. Or seed a dossier directly:
- **A report:** ask Cowork to copy `templates/person-dossier-template.md` to `people/<name>.md` and
  interview you to fill it (see how `people/daniel.md` was seeded).
- **A boss:** run `prompts/build-boss-profile.md` — it pulls from your **Gmail/Slack connectors** by
  default, with paste as a fallback.

### 5. Use the loops
Open a prompt file and ask Cowork to run it against the relevant dossier. For example:
> "Run `prompts/prep-1on1.md` against `people/marcus.md`."

See the [main README](../README.md) for the full workflow (prep → capture → reflect → digest).

---

## Keeping the kit updated
```bash
git pull            # get kit improvements (templates, prompts, playbooks, docs)
```
Because your data is gitignored, pulling updates to the kit never touches your private dossiers.

If you improve a **template or prompt** and want to share it back, commit just that file — your
`people/`/`boss/`/`decisions/` content won't be included.

---

## Other surfaces (not the primary path)

- **Claude Code (terminal/IDE):** same as Cowork — clone the repo, point Claude at it, run prompts
  against files. Fully supported.
- **Claude.ai Projects / Desktop chat (no filesystem):** you can still use the kit by uploading the
  `templates/`, `prompts/`, and `playbooks/` files into a **private Project's knowledge**, then having
  Claude generate and hold your dossiers as files within that Project. Workable, but more manual —
  you must keep the Project's copies of your dossiers up to date by hand, since Claude can't read a
  live folder. Prefer Cowork/Code if you have it.

---

## A note for sharing with peers
The **public repo is the shareable kit** — templates, prompts, playbooks, docs, and one fictional
example. It contains none of your real data. A peer clones it and seeds their own private dossiers
locally, exactly as above. That separation (public kit / private local data) is intentional — see
[PRINCIPLES.md](PRINCIPLES.md), P4 and P6.
