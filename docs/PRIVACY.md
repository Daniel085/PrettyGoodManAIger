# Privacy & Data Safety

This kit holds **candid, private notes about real coworkers** — performance reads, growth edges,
coaching judgments, plus your own decisions and reflections. That's the point (it's what makes the
advice non-generic), but it means you have to be deliberate about where the data lives and what you
feed the AI. Read this once before seeding real people.

---

## What to keep OUT of the AI

- Proprietary customer data, confidential financials, regulated material (PII, health, legal).
- Anything your employer hasn't explicitly blessed for use with AI tools.
- Secrets, credentials, security details.

**What's fine:** tone, communication style, decision-making patterns, your own observations about your
own behavior, and coaching judgments you'd be comfortable being accountable for. When in doubt, leave
it out — the system works on patterns, not secrets.

## ⚠️ Check your employer's policy

Before you put performance or personnel information about real coworkers into a work AI account, **check
your company's policy.** Some organizations treat performance data as restricted. Coaching observations
are often fine; assume nothing. This is a five-minute conversation that can save a real problem.

---

## Where your data lives: the public-package / working-copy split

There are two distinct things, and keeping them separate is the whole privacy model:

1. **The public package** (this repo) — templates, skills, prompts, playbooks, docs, and *fictional*
   examples. Zero real data. Shareable, publishable.
2. **Your working copy** — your live install with real dossiers, memory, and decisions. **Lives outside
   the public repo** (default `~/pgmanaiger-working/`, a sibling folder) and is **never committed.**

`/onboard` creates your working copy in a separate location for exactly this reason. If you instead run
the rituals inside this repo, the `.gitignore` is set up to ignore the live files (`Memory/`,
`Daily Notes/`, `Task Board.md`, real `people/`/`boss/`/`decisions/` content) as a backstop — but a
separate folder is safer and recommended.

## Verify your data is protected

After creating any real file, confirm it won't be committed:
```bash
git status                       # real dossiers should NOT appear as changes
git check-ignore people/<name>.md   # should print the path = it's ignored = safe
```

## If you accidentally tracked a private file

If a private file slipped into git before `.gitignore` caught it, untrack it (keeps your local copy,
removes it from the repo):
```bash
git rm --cached people/<name>.md
git commit -m "Remove accidentally-tracked private file"
```
If it was already **pushed** to a remote, treat the contents as exposed — the file lives in history.
For sensitive data, rewrite history (`git filter-repo`) or, more simply, rotate what was exposed and
consider the repo's history compromised for that file.

---

## The short version
- Real coworker notes → working copy, outside the repo, never committed.
- Check employer policy before seeding real people.
- Keep proprietary/confidential/regulated data out entirely.
- `git check-ignore` is your friend; `git rm --cached` is your recovery.
