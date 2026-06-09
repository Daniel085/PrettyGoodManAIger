# Skills Reference

The 11 skills that make up Pretty Good Man-AI-ger. On Claude Code / Cowork they're auto-discovered from
`.claude/skills/` and invoked as slash commands (`/start`, `/prep-1on1`, …). Each also has a
plain-prompt twin in `prompts/` for use in any LLM without the skills runtime (principle P6).

Skills fall into five groups: the **daily rituals** (the heartbeat), **managing down**, **managing up**,
**reflection**, and **synthesis** — plus a couple of **occasional** deep-build skills.

## At a glance

| Skill | When | Reads | Produces |
|-------|------|-------|----------|
| `/onboard` | once, at install | `templates/` | your working copy: memory, config, boss dossier; scheduled rituals; first `/start` |
| `/start` | every morning | memory, task board, calendar/tasks/email | a 5-line briefing + captured intentions; today's daily note |
| `/sync` | every mid-day | scratchpad, new meeting notes | sorted tasks/memory; proposed dossier updates (you approve) |
| `/wrap-up` | every evening | the day's notes | updated memory + accomplishments; optional decision log |
| `/prep-1on1` | before a report 1:1 | that report's dossier | a 60-second coaching brief |
| `/prep-boss-1on1` | before a boss 1:1 | the boss dossier + playbooks | a decision-room agenda packaged for that boss |
| `/capture-decision` | after a hard call | your 4 answers | a frozen decision file (prediction + revisit date) |
| `/reflect-on-decisions` | quarterly | `decisions/` | graded verdicts + calibration patterns; playbook candidates |
| `/weekly-digest` | weekly | everything | a Leadership Weather Report + ruthless top-3 |
| `/build-boss-profile` | occasionally | email/Slack with the boss | a deep boss dossier inferred from real history |
| `/extract-playbooks` | occasionally | `decisions/`, `people/` | proposed personal playbooks (evidence-cited) |

---

## Daily rituals — the heartbeat

These are scheduled (via `/onboard` → Routines) so capture happens *because the ritual ran*, not
because you remembered. They're the survival mechanism (principle P1).

### `/onboard` — first-run setup (once)
Interviews you (role, manager, stakeholders, tools, timezone, your shorthand), builds the
name-canonicalization map, seeds `Memory/memory.md` and one boss dossier, walks you through scheduling
the three rituals, and runs your first `/start`. Points you to `/build-boss-profile` for a richer boss
build. **Never writes real data into the public repo** — it sets up a separate working copy.

### `/start` — morning ritual
Reads memory first (always), then the task board and — if connected — today's calendar, new Jira/Linear
items, overnight email. Creates today's daily note. Hands you a **5-line synthesis** (top 3 priorities,
biggest unresolved decision, who needs attention, 1:1 prep, anything overdue), asks your intentions, and
offers to run prep for any 1:1s today. *Synthesizes, doesn't summarize; honest when data is thin.*

### `/sync` — mid-day ritual
Processes the scratchpad (every item → task board, memory, or deleted) and any new meeting notes
(action items, decisions, coaching signal). Updates the task board. **Proposes dossier updates as diffs
you approve** — for reports *and* the boss — never silently rewriting (principle P4). This is the ritual
that keeps every dossier current.

### `/wrap-up` — end-of-day ritual
Reflects on the day into the daily note, updates long-term memory (selectively — it's not a diary) and
`Accomplishments.md` (feedback/wins, while fresh), and offers to log a decision. Tone: encouraging.

---

## Managing down — your reports

### `/prep-1on1`
Reads a report's dossier and produces a 60-second brief: one-line read, open commitments both
directions (flags what you owe that's slipping), the current growth edge (or "discover it" if unknown),
recurring tension to watch, 2–3 coaching questions *specific to this person*, and what to bring/decide.
Ends with the single most important thing to get right. *Refuses to pad a thin dossier.*

---

## Managing up — your boss & stakeholders

### `/prep-boss-1on1`
Reads the boss dossier and turns your agenda into a **decision room**: decisions you need made,
blockers only they can clear, judgment calls you want their read on — pure status gets converted or
cut. Identifies genuine *advice-not-feedback* opportunities (and refuses to manufacture one). Packages
each item in the boss's archetype, format, and **currencies they value**, leading with the answer
(Pyramid). Pressure-tests for the questions you're not answering. Ends with a strength × warmth self-read.

### `/build-boss-profile` (occasional)
The deep build. Reads recent **email and Slack** with a boss/stakeholder to infer archetype, mutual
dependence, currencies, and preferred format — tagging every inference with source + confidence, and
naming what it couldn't determine. Use for the initial rich build, a new boss, or a refresh; routine
updates already happen via `/sync`. *Keeps proprietary/confidential content out — see PRIVACY.*

---

## Reflection — your own judgment

### `/capture-decision`
Pre-registers a judgment call **before** the outcome (the anti-hindsight-bias move): context, reasoning,
confidence, a falsifiable prediction, a revisit date. Saves a frozen file in `decisions/`. ~60 seconds;
won't inflate your confidence. Only for non-trivial calls worth grading later.

### `/reflect-on-decisions` (quarterly)
Two modes. **Revisit:** grade decisions past their revisit date, scoring *decision quality separately
from outcome luck* (right call–bad luck ≠ wrong call). **Pattern review:** surface calibration ("you're
over-confident on cross-team estimates"), blind spots, and strengths — with cited evidence. Once 6+
decisions are graded, proposes drafting personal playbooks. *Candid, not flattering; honest about thin data.*

### `/extract-playbooks` (occasional)
The compounding capstone. Mines `decisions/` and `people/` for repeated, working moves and codifies them
as playbooks in your voice — **evidence or it doesn't ship** (every play cites the instances behind it).
Declines honestly when history is too thin rather than inventing generic advice.

---

## Synthesis — the weekly step-back

### `/weekly-digest` (weekly)
Reads across memory, dossiers, decisions, daily notes, accomplishments, and the task board to produce a
**Leadership Weather Report**: the overall read, who needs attention, managing-up moves, decisions due
for revisit, blind-spot patterns, and a ruthless top-3 for the week ahead. *Synthesizes and prioritizes —
if everything's listed, nothing is surfaced.*

---

See [WALKTHROUGH.md](WALKTHROUGH.md) for these skills playing out across a real day, and
[PRINCIPLES.md](PRINCIPLES.md) for *why* each behaves the way it does.
