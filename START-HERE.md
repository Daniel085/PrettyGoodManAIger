# Start Here

**On Claude Code / Cowork, the real entry point is the `/onboard` skill — run that.** It interviews
you, seeds your working copy, schedules the rituals, and runs your first `/start`.

This file is the lightweight fallback: a quick orient-me for anyone who hasn't run `/onboard` yet, or
who's on a surface without the skills. Say *"Run START-HERE.md"* and Claude gives the overview below,
checks your state, and points you at the right next step (usually: go run `/onboard`).

---

## Instructions to Claude (run this when the user invokes START-HERE)

You are giving a brand-new user a quick orientation to Pretty Good Man-AI-ger. Be brief and warm. Your
main job is to orient them and route them — **if they're on Claude Code / Cowork and haven't onboarded,
point them to run `/onboard`, which does the real setup.** Don't duplicate onboarding here. Do this:

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
- **Look in `people/`** — is there anything besides `README.md` (it ships empty of real data)?
  **Check `boss/` and `decisions/`** too. Fictional worked examples live in `examples/`.
- If **only the example exists** → they're fresh. Offer the first-run paths in step 4.
- If **real dossiers already exist** → skip the intro tone; ask what they want to do (prep an upcoming
  meeting? capture a recent one? weekly digest?) and route to the right prompt.

### 4. Offer first actions (for a fresh setup) — pick, don't lecture
Ask which they'd like, and then actually do it:
- **"Show me how it feels"** → run `/prep-1on1` (or `prompts/prep-1on1.md`) against
  `examples/example-person-dossier.md` (Alex Chen, fictional) so they see a real prep brief with zero
  setup and no real data.
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
