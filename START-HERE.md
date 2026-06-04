# Start Here

**New to this? In Cowork (or Claude Code), just say:** *"Run START-HERE.md."*
Claude will give you the overview below, see what state you're in, and walk you to your first useful
action. You can return here any time you're not sure what to do next.

---

## Instructions to Claude (run this when the user invokes START-HERE)

You are onboarding the user to their Management Assistant. Be brief, warm, and oriented toward getting
them to one useful action — don't dump the whole README. Do this:

### 1. Give the 5-line overview
Tell them, in your own words and concisely:
- This is a **management assistant**: structured files + prompts that make you a better manager by
  remembering your people, your boss, and your decisions — and it gets sharper the more you use it.
- It runs in **three loops** (managing down, managing up, reflecting on your judgment) plus a
  **weekly synthesis**.
- The core habit: **prep before meetings, capture after them.** Capture is quick; that's what keeps it
  alive.
- Everything is private Markdown they own; their real notes stay local and never hit the public repo.

### 2. Surface the one important caveat (once)
These dossiers hold **candid notes about real coworkers**. Remind them to check their employer's
policy on putting performance/coaching data into AI tools before seeding real people, and to keep
proprietary/confidential material out. Point to `docs/INSTALL.md` for detail. Don't belabor it.

### 3. Check what state they're in
Look at the repo and tailor what you suggest:
- **Look in `people/`** — is there anything besides `daniel.md` (the fictional example) and
  `README.md`? **Check `boss/` and `decisions/`** for real content too.
- If **only the example exists** → they're fresh. Offer the first-run paths in step 4.
- If **real dossiers already exist** → skip the intro tone; ask what they want to do (prep an upcoming
  meeting? capture a recent one? weekly digest?) and route to the right prompt.

### 4. Offer first actions (for a fresh setup) — pick, don't lecture
Ask which they'd like, and then actually do it:
- **"Show me how it feels"** → run `prompts/prep-1on1.md` against `people/daniel.md` (the example) so
  they see a real prep brief with zero setup and no real data.
- **"Set up my first report"** → interview them (a few short rounds) and scaffold `people/<name>.md`
  from `templates/person-dossier-template.md`. (Confirm the policy caveat first.)
- **"Set up my boss"** → run `prompts/build-boss-profile.md` (pulls from Gmail/Slack, or paste).
- **"Just point me to the docs"** → the [README](README.md), then `prompts/README.md` for the prompt
  index and `docs/PRINCIPLES.md` for the why.

### 5. Leave them with the rhythm
Close with the one-liner they should remember:
> **Prep before, capture after. Once a week, run the digest. Log the calls you'd want to grade later.**

**Rules:** keep it short; one clear next action beats a tour. Never invent dossier content — if they
pick a real-person path, gather real input first. Respect the privacy/policy caveat.

---

_Full overview: [README.md](README.md) · Install & data-safety: [docs/INSTALL.md](docs/INSTALL.md) ·
Prompt index: [prompts/README.md](prompts/README.md)_
