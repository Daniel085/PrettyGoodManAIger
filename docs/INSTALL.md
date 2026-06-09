# Install & Setup

How to get Pretty Good Man-AI-ger onto your machine and running in Claude. The recommended setup is
**Claude Cowork (or Claude Code) with a local clone of the repo** — it reads the folder directly and
auto-discovers the skills, which is exactly how the system is designed to run. For the full
architecture and the public-package-vs-working-copy model, see [../SETUP.md](../SETUP.md).

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
The repo ships a `.gitignore` that keeps real dossiers out of version control. Verify it's working
**before** you create any real notes:
```bash
git status                          # a real people/<name>.md should NOT appear as a change
git check-ignore people/yourreport.md   # should print the path = it's ignored = safe
```
Only the folder READMEs and `.gitkeep` placeholders are tracked in `people/`/`boss/`/`decisions/`;
fictional worked examples live in `examples/`. Everything you create in those data folders stays local.
Better still, keep your real data in a **separate working copy** outside the repo — see
[PRIVACY.md](PRIVACY.md) and [../SETUP.md](../SETUP.md).

### 4. Run `/onboard`
On Cowork / Claude Code the skills in `.claude/skills/` are auto-discovered, so just run **`/onboard`**.
It interviews you, seeds your working copy (memory + boss dossier), helps you schedule the daily
rituals, and runs your first `/start`. (Not sure where to start? "Run START-HERE.md" for a quick
orientation that points you here.)

### 5. Live in the rituals
`/start` each morning, `/sync` after lunch, `/wrap-up` at end of day; `/prep-1on1` and
`/prep-boss-1on1` before meetings. To try it with zero setup, run `/prep-1on1` against
`examples/example-person-dossier.md` (fictional). See [../SETUP.md](../SETUP.md) and the
[main README](../README.md) for the full workflow.

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
The **public repo is the shareable kit** — skills, templates, prompts, playbooks, docs, and fictional
examples. It contains none of your real data. A peer clones it, runs `/onboard`, and seeds their own
private working copy locally. That separation (public kit / private local data) is intentional — see
[PRINCIPLES.md](PRINCIPLES.md), P4 and P6, and [PRIVACY.md](PRIVACY.md).
