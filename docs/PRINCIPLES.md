# Architectural Principles

This document explains *why* the Management Assistant is built the way it is. Every structural
choice — the dossier schemas, the capture/prep split, the two loops, the playbooks — descends from a
principle below. Principles are grouped into **system-design principles** (how the kit behaves as a
piece of software-shaped tooling) and **management principles** (the ideas about leadership it
encodes). Sources are cited inline and collected in [REFERENCES.md](REFERENCES.md).

---

## Part 1 — System-design principles

### P1. Capture must be cheaper than the value it returns
**The principle.** A personal knowledge system survives only if the cost of feeding it is reliably
lower than the value it gives back. A system that depends on willpower — a heroic weekly ritual —
decays within weeks, because life eats the ritual. So every design decision is evaluated against one
question: *does this make capture cheaper, or does it tax it?*

**How it shows up in the architecture.**
- `capture-post-1on1.md` is designed for a ~90-second human cost: paste raw notes, the AI does the
  extraction and structuring, you only approve.
- The dossier templates pre-define the slots, so capture is *filling a known shape*, not authoring
  prose.
- `build-boss-profile.md` defaults to pulling from connectors (Gmail/Slack) rather than asking you to
  assemble inputs by hand.

**Why we believe it.** The source talk is explicit that the three core moves "are not free" and
that the cost is exactly why managers "wing it, or shortchange it, or don't do it at all"; the entire
pitch for AI here is to "dramatically bring down the cost" of capture and prep (Kline & Marsden). We
treat that as the load-bearing constraint, not an afterthought.

### P2. Data before payoff (the dependency chain)
**The principle.** The components form a strict chain: `schema → capture → accumulated data → prep →
compounding`. A payoff prompt run against an empty or stale dossier produces exactly the generic AI
advice the system exists to beat. So you always seed real data before expecting real value, and you
build the capture side before leaning on the query side.

**How it shows up.** We built and seeded a real report dossier (`people/daniel.md`) and the capture
prompt *before* relying on prep. On the managing-up side, `build-boss-profile.md` (capture) is a
prerequisite for `prep-boss-1on1.md` (payoff), and the prep prompt says so.

### P3. Separate the observed from the inferred
**The principle.** The most dangerous failure mode of an AI memory system is laundering a guess into a
remembered fact. Once "I think Daniel's edge is exec presence" becomes "Daniel's edge is exec
presence," every downstream prep inherits the error with false confidence.

**How it shows up.** Every claim in a dossier carries a citation tag —
`[src: 1:1 | 2026-06-02 | confidence: high|med|low]` — and `[src: inference]` is visually distinct
from `[src: interview]` or `[src: email]`. Capture and prep prompts are instructed to keep
hypotheses labeled as hypotheses and to be conservative with confidence ("one conversation rarely
justifies high confidence"). The citation-and-confidence discipline is borrowed directly from the
open-source COG-second-brain project (MIT).

### P4. Append-only history; approve, don't overwrite
**The principle.** The current "best understanding" of a person changes, but the *record of how it
changed* is itself valuable — it's what lets you ask "was my read right?" later. And the human must
stay the editor: the AI proposes, you dispose.

**How it shows up.** Every dossier has a two-layer structure (borrowed from COG-second-brain):
**Compiled Truth** (current best understanding, rewritten as evidence changes) plus an **append-only
Timeline** (dated entries, never rewritten). Material changes to Compiled Truth leave the superseded
claim in the Timeline. `capture-post-1on1.md` outputs a *proposed diff you approve* rather than
silently rewriting the file — this is both a trust mechanism and a safeguard against P3 errors.

### P5. Specialize over generalize
**The principle.** The entire value proposition is that specificity beats generic advice. A template
that tries to serve every manager can't contain the fields that make advice sharp; a template that
knows it's for Product/Design managers of ICs can. When building for a known audience (you + a few
peers), specialize.

**How it shows up.** The report dossier carries product/design-specific craft fields (discovery vs.
delivery vs. strategy, stakeholder friction, exec presence, saying-no). The capture prompt is told to
mine for exactly those signals. We deliberately did *not* pre-load generic frameworks as the
foundation — the defensible asset is your data, not commodity content available everywhere.

### P6. Platform-agnostic, file-based, ownable
**The principle.** The brain is plain Markdown you own, not data locked in an app. This maximizes
portability (runs in Claude/Cowork, ChatGPT, Gemini, Copilot), longevity, and trust.

**How it shows up.** Everything is `.md`. Prompts are documents you open alongside files, not API
calls. The recommended runtime is Claude / Cowork (which the source talk found most reliable,
versus the fragmented security postures of Copilot installs), but nothing hard-depends on it.

### P7. Compounding is the product
**The principle.** The file is not the asset — the *feedback loop* is. A dossier that never updates is
a stale note; a dossier wired into a capture→prep→refine cycle is a living assistant. We optimize for the
loop closing, not for any single artifact being perfect.

**How it shows up.** Three loops are explicitly closed: report prep consumes what report capture
produces; boss prep consumes what the profile builder produces (with a "refine mode" that folds
post-meeting reality back in); and the decision log captures calls that `reflect-on-decisions.md` later
grades and mines for patterns. The decision log's payoff is the slowest (months, at revisit) — a
direct consequence of P2: it can't produce value until there's history to compound, which is also why
**playbook extraction** stays deferred until the log has accumulated enough decisions to mine.

---

## Part 2 — Management principles encoded in the system

These are the leadership ideas the kit operationalizes. They come from the source talk and the
classic literature it stands on.

### M1. Synthesize big from small — command, not status
**The idea.** The leaders who get ahead aren't the ones with longer status updates; they're the ones
who synthesize what matters from the detail and take a stand. Vagueness reads as "doesn't know what's
going on"; an exhaustive laundry list reads as "can't tell what matters." A *synthesis* (what truly
matters) is not a *summary* (an exhaustive retelling). And: "the quality of your communication is a
direct reflection of the quality of your thinking" (Kline & Marsden).

**Where it lives.** `playbooks/synthesis-30-second-update.md` (state → trend → biggest problem →
solution + confidence, in proper nouns and numbers, not jargon) and `playbooks/scqa-and-pyramid.md`
(SCQA to structure thinking; the Pyramid Principle — answer first — to deliver it). Prep prompts
enforce "decisions over reporting." At the system level, `weekly-digest.md` applies the same
discipline to your whole leadership picture: a Leadership Weather Report that synthesizes and
prioritizes rather than listing everything.

### M2. Managing up is mutual dependence, not flattery
**The idea.** The boss relationship is one of *mutual dependence between two fallible people* — not a
target to manipulate or a superior to appease. Your boss depends on you for reliability, honesty, and
information (no surprises); you depend on them for resources, priorities, and air cover. Managing it
well means understanding *both* their world and your own needs and predispositions (Gabarro & Kotter,
"Managing Your Boss," HBR 1980).

**Where it lives.** The boss dossier's **Mutual Dependence** and **Understand Yourself** sections map
both sides of the dependency, including the three deliverables of a good boss relationship (keep them
informed / be dependable & honest / use their time selectively) and your own predisposition toward
authority (counter-dependent vs. over-dependent).

### M3. Decode the person; communicate what they need to hear
**The idea.** "You are not communicating what you want to say; you are communicating what they need to
hear" (Kline & Marsden). Different bosses are wired differently — bottom-line, data-driven,
storytelling/relationships, detail-anxious/FOMO — and you must package your message in *their* format
and "love language," not yours. AI is good at building this profile from the communications you
already have.

**Where it lives.** The boss dossier's **Archetype** and **Love Language / Preferred Format** fields;
`build-boss-profile.md`, which infers them from real email/Slack; and `prep-boss-1on1.md`, which
re-packages every agenda item into the boss's archetype and format.

### M4. Influence runs on currencies you can exchange
**The idea.** You gain cooperation — especially where you lack authority — by offering what the other
person values, in the "currencies" they care about: inspiration (vision, excellence), task (resources,
information), position (recognition, advancement), relationship (gratitude, acceptance), personal
(autonomy, meaning) (Cohen & Bradford, "Influence Without Authority"). This turns managing up from a
vibe into a concrete, plannable exchange.

**Where it lives.** The boss dossier's **Currencies They Value** section, and `prep-boss-1on1.md`,
which frames asks in terms of "what's in it for them."

### M5. Influence = strength × warmth
**The idea.** Influence comes from balancing strength (competence, confidence) with warmth (empathy,
trust); most people over-index on one. "Data makes them believe you; story makes them remember you,"
and "we give more grace to people we like" (Kline & Marsden, echoing Neffinger & Kohut, "Compelling
People"). This is primarily a *self*-diagnostic: which am I projecting, which does this relationship
need more of?

**Where it lives.** The boss dossier's **Understand Yourself → Strength × Warmth** self-read; the
"balance data and story" guidance in the synthesis playbook.

### M6. Ask for advice, not feedback (and only on high-stakes calls)
**The idea.** Counterintuitively, asking for *advice* on a hard, ambiguous, high-stakes call makes you
rated *more* competent (effect strongest on the hardest problems) and converts your boss from an
auditor into a co-owner — it "smears their fingerprints all over it." Word choice matters: "advice" or
"help," not "feedback." The guardrail: overuse on things you should handle yourself *inverts* the
effect and erodes trust (Kline & Marsden, citing the advice-seeking competence research).

**Where it lives.** `playbooks/advice-not-feedback.md` (with the guardrail front and center), and
`prep-boss-1on1.md`, which identifies genuine advice-not-feedback opportunities and refuses to
manufacture one when nothing qualifies.

### M7. The 1:1 is a decision room, not a status update
**The idea.** A status 1:1 makes you a reporter ("here's what I did") and leaves your boss wondering if
you're capable of more. A decision-driven 1:1 makes you a leader: you walk in with the asks, the
blockers only they can clear, and the judgment calls you want their read on — and you leave with
decisions *made* (Kline & Marsden). The same posture (develop, don't just track) applies managing
down.

**Where it lives.** `playbooks/one-on-one-as-decision-room.md`; both prep prompts, which convert
status items into decisions/asks or cut them.

### M8. Develop people, including the difficult cases
**The idea (managing down).** A report's dossier exists to help you *develop* them, not just collaborate
with them — which is why these are candid, private coaching notes (judgments and growth edges
included), deliberately unlike a neutral "shareable" contacts CRM. The hardest, highest-value part of
management is the difficult 20%: people who resist improving.

**Where it lives.** The person dossier's **Growth Edge**, **Coaching Notes**, and the private-note
framing; `prep-1on1.md`, which makes "discover and coach the growth edge" the implicit goal of each
1:1 and refuses to pad when the dossier is thin.

### M9. Judge decisions by their quality, not their outcome
**The idea.** Good judgment is learnable, but only if you separate the *quality of a decision* from the
*quality of its outcome* — a sound call can go wrong (bad luck) and a poor call can go right (good
luck). Because hindsight silently rewrites what you "knew," the only honest way to calibrate is to
record your reasoning and confidence *before* the result is in, then revisit. Over many decisions, the
patterns reveal where you're over- or under-confident and what kind of call you systematically miss
(Duke, "Thinking in Bets"; Kahneman; the decision-journal practice; ADR structure).

**Where it lives.** The decision log: `templates/decision-template.md` (frozen pre-registered
prediction + a separate, later Outcome section), `capture-decision.md` (log before you know),
`reflect-on-decisions.md` (grade decision-quality vs. luck; surface calibration and blind spots). This
is also the feedstock for extracting your own playbooks (P7).

---

## How the principles interact

The system-design principles keep the tool *alive* (P1, P2) and *trustworthy* (P3, P4); the
specialization and platform choices keep it *valuable and ownable* (P5, P6); and the whole thing only
becomes a living assistant rather than a notes folder because of the compounding loop (P7). The
management principles (M1–M9) are the *content* those mechanics carry — and they're drawn from
durable, cited sources rather than one talk's hot take, which is what lets this kit be handed to a
peer as a credible system rather than a personal hack.
