# FAQ & Troubleshooting

Straight answers, including where the system bends. Pretty Good Man-AI-ger has real failure modes — it
relies on rituals being scheduled and on honest self-capture, and it takes a couple of weeks before it
pays off. Better you know that up front.

---

## Getting value

### How long until it's actually useful?
About **two to three weeks.** The first fortnight is investment: you're seeding dossiers and building the
capture habit, and a prep brief over a thin dossier is just generic AI (see principle P2 — data before
payoff). Compounding shows up around week three, when there's enough history that the briefings and the
weekly digest start telling you things you'd have missed. If you bail in week one, you'll conclude it
doesn't work — fairly, because it hasn't had data yet.

### It gave me generic, obvious output. What's wrong?
Almost always: **the dossier or memory is thin.** These skills are only as good as what they read. A
`/prep-1on1` against a near-empty dossier can't be specific. The fix isn't a better prompt — it's a few
more `/sync` cycles capturing real signal. The skills are written to *admit* when they're thin rather
than pad (`/prep-1on1` will say "I don't know this person's growth edge yet"); if you're getting
confident-but-generic output, that's the signal to feed it more.

### The rituals keep not happening.
This is **the** failure mode — the reason systems like this die. Two defenses:
1. **Schedule them** (during `/onboard`, via Claude Code Routines). An unscheduled ritual is back to
   willpower, and willpower loses to a busy week.
2. **Protect the 90-second capture.** The keystone habit is dumping raw notes right after a meeting.
   Everything downstream depends on it. If you do nothing else, do that.
If you've fallen off, just run `/start` again — there's no penalty for a gap, and the system picks back up.

---

## Setup & surfaces

### Do I need Claude Code, or does this work elsewhere?
**Claude Code / Cowork is the intended home** — it auto-discovers the skills (slash commands) and can
read your working folder directly, which is what makes the rituals frictionless. But every skill has a
plain-prompt twin in `prompts/`, so you can paste those into ChatGPT, Gemini, or Claude.ai and run the
same logic by hand (principle P6). You lose the slash-command convenience and the live folder reads;
you keep the substance.

### What if I don't have Jira / Slack / Gmail / Calendar connected?
Fine. The rituals check connectors **opt-in** and skip silently when one's missing — `/start` just
won't include calendar items, `/build-boss-profile` falls back to pasted comms. Nothing fails loudly.
Connect what you have; the system degrades gracefully.

### How do the scheduled rituals work — is it true cron on my machine?
No. Claude Code **Routines** run on Anthropic's cloud infrastructure (so they fire even when your laptop
is closed), with a **1-hour minimum** interval. That's fine for daily morning/mid-day/evening triggers.
`/loop` is the other option but only runs while a session is open. If you'd rather not automate, just
type `/start`, `/sync`, `/wrap-up` yourself at those times.

---

## Data & privacy

### Is my data safe? Where does it live?
Your real notes live in a **separate working copy** (default `~/pgmanaiger-working/`), **outside** this
repo, and are **never committed**. The public repo ships only templates, skills, and *fictional*
examples. As a backstop, the `.gitignore` also ignores real dossiers and live ritual files if you ever
run them inside the repo. Verify with `git check-ignore people/<name>.md`. Full detail in
[PRIVACY.md](PRIVACY.md).

### Can I use this with notes about real coworkers on my work account?
Maybe — **check your employer's policy first.** These dossiers contain candid performance and coaching
judgments; some organizations restrict putting personnel data into AI tools. Coaching observations are
often fine; assume nothing. And keep proprietary/customer/confidential material out entirely (tone,
format, and decision-style are fine; secrets are not).

### I accidentally committed a private file. Help.
Untrack it (keeps your local copy):
```bash
git rm --cached people/<name>.md
git commit -m "Remove accidentally-tracked private file"
```
If it was already **pushed**, treat the contents as exposed (it lives in history) — rotate anything
sensitive and consider rewriting history with `git filter-repo`. See [PRIVACY.md](PRIVACY.md).

---

## Using it well

### What counts as a decision worth logging?
A **non-trivial call you could reasonably have gone the other way on**, where you'd learn something from
being right or wrong — a prioritization, a people call, an escalation, a bet. *Not* routine or obvious
decisions. If future-you would want to grade it, log it. Over-logging dilutes the calibration signal;
`/capture-decision` will gently steer you off trivial ones.

### Why "advice," not "feedback," when managing up?
Because asking for *advice* on a genuinely hard call makes you read as more competent and pulls your boss
in as a co-owner — where "feedback" is vague and backward-looking. It's a real, research-backed
distinction (see `playbooks/advice-not-feedback.md`). The guardrail: only on high-stakes, ambiguous
calls — overuse on routine things inverts the effect. `/prep-boss-1on1` won't manufacture an advice-ask
when nothing qualifies.

### My dossiers are getting long. Should I trim?
Memory: yes, aggressively — it's for what future-Claude needs with zero context, not a diary; `/wrap-up`
trims stale items. Dossiers: the **Compiled Truth** stays lean (current best understanding) while the
**Timeline** grows append-only — that's by design (principle P4). If Compiled Truth is sprawling, that's
a sign to consolidate it and push the history down into the Timeline.

### Can the system learn *my* way of managing?
Yes — that's `/extract-playbooks`. Once you've logged enough decisions and 1:1s, it mines them for your
repeated, working moves and proposes playbooks in your voice — but only with cited evidence, and it
declines when history is too thin. It's the compounding capstone, and it's deliberately patient.

---

Still stuck? The design rationale for any behavior is in [PRINCIPLES.md](PRINCIPLES.md); the per-skill
detail is in [SKILLS.md](SKILLS.md).
