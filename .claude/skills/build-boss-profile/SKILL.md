---
name: build-boss-profile
description: Deep-build or rebuild a boss / skip / stakeholder dossier from real history — reads your recent email and Slack with them to infer archetype, currencies, and preferred format. Run occasionally (initial build, new boss, or a refresh), not daily — routine updates happen via /sync.
invoke: both
---

# /build-boss-profile — deep build from history

You are building (or rebuilding) a PRIVATE managing-up dossier for a boss, skip-level, or key
stakeholder, using the `boss-dossier-template.md` schema. This is the **occasional deep build** —
day-to-day updates already happen via `/sync` from meeting notes, so use this for: the initial rich
build, a new boss, or a periodic refresh. (Full reference: `prompts/build-boss-profile.md`.)

**Default sources = the user's connectors.** Search **Gmail** and **Slack** for recent threads/messages
with this person (last ~2–3 months) and read the substantive ones for tone, format, what they reward,
what makes them anxious, how they decide. Fall back to pasted comms if connectors aren't available.

> SECURITY: keep proprietary/customer/confidential content out of the profile unless company-blessed.
> Tone, format, decision style, and pressures are fine; secrets are not. (See `docs/PRIVACY.md`.)

Produce a draft filling the template:
- **Archetype** (bottom-line / data-driven / storytelling-relationships / detail-anxious-FOMO — often a
  blend), with cited evidence.
- **Mutual Dependence** (Gabarro & Kotter), **Their World**, **Currencies They Value** (Cohen &
  Bradford), **Love Language / Preferred Format** — inferred from how *they* actually communicate.
- **Understand Yourself / Strength × Warmth** — leave prompts for the user; don't invent their side.
- Scaffold the rest (Conflict Map, What Lands, Open Asks, Commitments, Timeline).

**Rules:**
- Tag every inferred claim `[src: email|slack | <date> | confidence: ...]`; be honest about confidence —
  a profile from a handful of messages is mostly `low`/`med`.
- Separate **observed** (their actual words) from **inferred** (your read of what it means).
- State explicitly what you COULDN'T determine, so the user knows what to watch for in person.
- **Refresh mode:** if given a fresh transcript and "this landed / went sideways at minute N," update
  the relevant sections and append a dated Timeline entry — never rewrite history.
- Propose the file as `boss/<name>.md` for the user to approve before writing.
