# Prompt: Build / Refine a Boss Profile

**When:** to create a managing-up dossier for a boss, skip-level, or key stakeholder — or to refine
one after a meeting. Based on Kline & Marsden's method: feed in real communications, let AI infer the
profile, then keep refining it over time.

**Default sources = your connectors.** Most Claude / Cowork setups have email and Slack connected:
- **Gmail** — search threads with this person, then read the substantive ones for tone, format,
  what they reward, what makes them anxious, how they decide.
- **Slack** — DMs and channel messages with/from them. (If Slack isn't connected yet, it's a
  one-time authorize; otherwise just paste a few representative messages.)
- **Fallback — paste:** drop in emails, Slack, meeting notes, past feedback, last 1:1 transcript.

> SECURITY: keep proprietary/customer/confidential content out of the profile unless company-blessed.
> Tone, format, decision style, and pressures are fine; secrets are not.

---

## Instructions to the AI

Build (or refine) a PRIVATE managing-up dossier on the named person, using the
`boss-dossier-template.md` schema. The goal is to decode how they need to be led so I can
communicate what they NEED TO HEAR.

**Gather first:**
1. If Gmail/Slack connectors are available, search for recent threads/messages with this person
   (last ~2–3 months) and read the substantive ones. Tell me what you pulled and from where.
2. If connectors are unavailable or thin, ask me to paste, or work from what I provide.

**Then produce a draft dossier filling every section of the template:**
- **Archetype** — bottom-line / data-driven / storytelling-relationships / detail-anxious-FOMO
  (often a blend). Cite the evidence.
- **Mutual Dependence** (Gabarro & Kotter) — what they depend on me for, what I depend on them for.
- **Their World** — measured on, pressures, decide-by, processes verbal/written, rewards, anxieties,
  blind spots.
- **Currencies They Value** (Cohen & Bradford) — which currencies show up, and what I could offer.
- **Love Language / Preferred Format** — the format that lands; what makes them disengage. (Infer
  from how THEY write: length, structure, emoji, data vs. story.)
- **Understand Yourself / Strength × Warmth** — leave prompts for me; don't invent my side.
- Leave **Conflict Map**, **What Lands**, **Open Asks**, **Commitments**, **Timeline** scaffolded.

**Rules:**
- Tag every inferred claim `[src: email | <date> | confidence: ...]` etc. Be honest about confidence —
  a profile from a handful of messages is mostly `low`/`med`.
- Separate **observed** (their actual words/behavior) from **inferred** (your read of what it means).
- Note explicitly what you COULDN'T determine, so I know what to watch for in person.
- **Refine mode:** if I provide a fresh transcript and say "this landed / this went sideways at
  minute N," update the relevant sections and append a dated Timeline entry — don't rewrite history.

---

## Context
- Person & relationship: `<name — manager | skip-level | board | stakeholder>`
- Sources to use: `<default: Gmail + Slack connectors; or "pasted below">`
- Output file: `boss/<name>.md`
