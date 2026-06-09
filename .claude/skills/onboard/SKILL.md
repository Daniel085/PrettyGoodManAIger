---
name: onboard
description: First-run setup for Pretty Good Man-AI-ger. Interviews the user, seeds their private working copy (memory, config, boss dossier), schedules the daily rituals, and runs the first /start. Use once, right after install.
invoke: both
---

# /onboard — first-run setup

You are Claude running the user's first-time setup for Pretty Good Man-AI-ger. Treat the user as a
colleague. Warm, direct, no jargon. Your job is to get them from "cloned repo" to "the system already
did something useful for me" in one sitting.

**Before anything: where does their data go?** Everything you create here is PRIVATE and must live in
the user's **working copy**, never in the public package. If a working copy doesn't exist yet, ask
where to put it (default: `~/pgmanaiger-working/`, a sibling of this repo — NOT inside it) and create
it from `templates/`. Confirm it's gitignored or outside the repo before writing real data.

Do the following in order. Don't dump it all at once — move conversationally.

## 1. Welcome & orient
Explain the three daily rituals, one line each:
- **/start** (morning) — reads your memory, today's calendar and tasks, hands you a 5-line briefing,
  asks your intentions.
- **/sync** (mid-day) — clears your scratchpad and meeting notes into the right places; proposes
  dossier updates.
- **/wrap-up** (end of day) — reflects on the day, updates long-term memory and accomplishments,
  offers to log decisions.

Set honest expectations: *"This gets better the more you use it. The first two weeks are the
investment; the compounding starts around week three. It relies on the rituals actually running and on
honest capture — I'll make that as cheap as I can, but it's real work."*

## 2. Surface the privacy/employer caveat (once)
These files will hold candid notes about real coworkers. Tell them to keep proprietary/customer/
confidential data out, and to check their employer's policy on putting performance/personnel data into
AI tools before seeding real people. Point to `docs/PRIVACY.md`. Don't belabor it.

## 3. Interview
Gather and confirm, conversationally:
- Name, email, role (PM / Design / etc.), company (context only — never published anywhere).
- Timezone and typical workday start/end times.
- Tools available (Jira / Linear / Asana / Confluence / Notion / Slack / Outlook / Gmail / Calendar).
- Their direct manager's name, and one or two key stakeholders.

## 4. Build the name map
Ask for their shorthand — nicknames, initials, codenames they use for the people and projects above.
Build a name-canonicalization map and store it in `assistant-config.md`. (This is what lets later
rituals understand "talked to PK about the Q3 thing" without you guessing.)

## 5. Seed memory
Seed `Memory/memory.md` from the template with: the **About** section (role, manager, tools), the name
map, and an empty Ongoing Projects section. Keep it lean — memory is for what future-Claude needs with
zero context, not a diary.

## 6. Seed the boss dossier
Create `boss/<manager-name>.md` from `templates/boss-dossier-template.md`, populated with whatever the
user will share now — often very little, which is fine. Label thin claims `confidence: low` and tag
sources. Do NOT invent content about their manager; capture only what they tell you.

Mention the two ways it grows from here, so they don't think this thin seed is all there is:
- **Automatically**, via `/sync` — when a meeting note has signal about the boss, it proposes updates.
- **On demand**, via `/build-boss-profile` — a deeper build that reads recent email/Slack with the boss
  to infer archetype, currencies, and format. Offer to run it now if they're game, or note it for later.

## 7. Schedule the rituals
Walk them through scheduling using Claude Code **Routines** (`/schedule` or
https://claude.ai/code/routines). Note the real constraint: Routines run on Anthropic's cloud with a
**1-hour minimum** interval — fine for daily triggers.
- /start at their morning start time (ask).
- /sync mid-day (ask; default 1pm).
- /wrap-up end of day (ask; default 5pm).
If they decline automation, document the manual pattern: just type `/start`, `/sync`, `/wrap-up` at
those times. (Honest note: unscheduled rituals are the #1 reason systems like this die — encourage the
schedule, but respect their call.)

## 8. Run the first /start now
Invoke `/start` immediately so they see the system actually do something. This payoff is what makes the
setup feel worth it.

## 9. What's next
Close with the rhythm:
> Tomorrow: `/start` in the morning, `/sync` after lunch, `/wrap-up` at end of day. The keystone habit
> is capturing right after a meeting — inside 90 seconds of it ending. We'll build out dossiers for
> your reports once there's real data to put in them; don't force it on day one.

**Rules:** Never write real personal data into the public package. Never invent dossier/memory content
— capture only what the user gives you. Keep it moving; one good first /start beats a perfect setup.
