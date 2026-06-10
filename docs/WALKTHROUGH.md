# A Day in the Life

What Pretty Good Man-AI-ger actually feels like in use — one Tuesday, played out. This uses the
fictional examples that ship with the kit (`examples/`): **Alex Chen**, a senior PM who reports to you,
and **Sam Rivera**, your director. The outputs below are **illustrative** — yours depend on your real
data — but they show the shape of what each ritual produces.

> New here? Read the [README](../README.md) first for the what-and-why; this is the how-it-feels.
> Want to *live* it instead of reading it? The [`demo/`](../demo/README.md) folder is this exact
> scenario as a pre-seeded working copy — run the rituals against it yourself.

---

## 8:30am — `/start`

You sit down with coffee and run `/start` (or it already ran on schedule and the briefing is waiting).
It reads your memory and task board, glances at your calendar, and hands you:

> **Tuesday briefing.**
> - **Top 3:** (1) Unified-inbox v1 scope decision — eng wants 6 wks, Alex wants the full spec; (2)
>   prep the CPO pre-read Sam needs by Thursday; (3) unblock the design review for Activation.
> - **Biggest unresolved decision:** the v1 scope cut. It's been open 3 days; Aug 20 advisory demo is
>   the forcing function.
> - **Who needs attention:** Alex — your 11:00 1:1, and the Marco/eng friction is still open from last
>   week.
> - **Prep needed:** 1:1 with Alex at 11:00. Want me to run `/prep-1on1`?
> - **Overdue:** the Staff-readiness self-assessment you asked Alex for (due last Friday).
>
> What are your intentions for today?

You type: *"Land the v1 scope call with eng, and make the Alex 1:1 about the Staff path, not status."*
It captures that in today's daily note. You say yes to the prep.

---

## 10:50am — `/prep-1on1` (Alex)

Right before the 1:1, you run `/prep-1on1`. It reads `people/alex-chen.md`:

> **Alex Chen — 1:1 prep.**
> - **Read:** Strong discovery PM at a Staff inflection; the gate is exec presence, not craft.
> - **Open commitments:** *You owe Alex* a mediated retro with Marco (committed Apr 22 — now slipping,
>   worth acknowledging). *Alex owes you* the Staff-readiness self-assessment (overdue since Friday).
> - **Growth edge:** exec presence — over-explains to leadership, buries the headline. Today's a chance
>   to coach it directly.
> - **Tension to watch:** the Marco/eng friction since the March slip. Alex feels blamed.
> - **Coaching questions:** (1) "When you presented at the QBR, what were you trying to make them feel?"
>   (2) "What's the one sentence you'd want Sam to remember from the inbox project?" (3) "What's blocking
>   the self-assessment — is the Staff goal still the one you want?"
> - **The one thing to get right:** make this about *his* growth trajectory, not project status — and
>   own the slipping Marco commitment before he raises it.

You walk in actually ready. The conversation goes well; Alex admits the Staff goal feels daunting, and
you agree to pair on the next CPO review as a deliberate exec-presence rep.

---

## 11:45am — capture (30 seconds)

Straight after, you dump raw notes into your scratchpad (or a meeting note) — no structure, just:

> *alex 1:1 — staff goal still wants it but nervous. paired him on CPO review prep as exec-presence rep.
> he'll send self-assessment thurs. marco retro — i apologized it slipped, scheduling this week. he
> seemed relieved.*

That's it. You go to lunch. The structuring happens later, automatically.

---

## 1:00pm — `/sync`

Mid-day reset. `/sync` processes that scratchpad note and proposes:

> **From your Alex note, I'd update `people/alex-chen.md`:**
> - **Commitment (done):** "find an exec-visibility opportunity" → the CPO review pairing fulfills it.
> - **Commitment (new):** You → Alex, schedule the Marco retro this week (`open`).
> - **Commitment (new):** Alex → You, Staff self-assessment by Thursday (`open`).
> - **Timeline entry (Jun 9):** "Career 1:1 — Staff goal confirmed but anxiety surfaced; paired on CPO
>   review as exec-presence rep." `[src: 1:1 | 2026-06-09 | confidence: high]`
> - **Coaching note:** "Responds to being given a concrete rep, not abstract advice." `[src: inference |
>   2026-06-09 | confidence: med]`
>
> Approve these?

You approve. Alex's dossier is now current — and you didn't write a word of structured prose. Scratchpad
clear.

---

## 3:00pm — the scope call + `/capture-decision`

You make the call: ship v1 with the top 2 channels, defer the rules engine, hit the Aug 20 demo. It's a
real judgment call you could've gone either way on — so you run `/capture-decision`:

> *Decided: 2-channel v1, defer rules engine. Why: the demo date is a hard external commitment and 2
> channels cover ~80% of demand; reversible if wrong. Expect: demo Aug 20, GA by Sep 15, activation lift
> within 30 days. ~70% confident. Revisit Aug 1.*

It writes `decisions/2026-06-09-scope-down-v1-inbox.md`, frozen, Outcome section empty. In August,
`/reflect-on-decisions` will surface it and ask how it actually went — and you'll grade your judgment
honestly, because you can't rewrite what you predicted today.

---

## 5:15pm — `/wrap-up`

End of day. `/wrap-up` reflects with you:

> **Today:** Landed the v1 scope call (logged). Good Alex 1:1 — moved it to the Staff path as you
> intended. Marco retro still to schedule.
> - **Memory:** noting the inbox scope decision in Key Decisions (affects the roadmap).
> - **Accomplishments:** added "drove unified-inbox v1 scope decision under demo deadline."
> - **Slipping:** the Marco retro — carried to tomorrow.
> Nice work today. Want me to draft tomorrow's intentions?

---

## Friday — `/weekly-digest`

At week's end, the **Leadership Weather Report** reads across everything:

> **The weather:** Steady, one front moving in. Inbox v1 is unblocked and shipping to a clear deadline;
> the open risk is Alex's exec-presence development colliding with the CPO review in two weeks.
> - **People:** Alex needs the most attention — Staff anxiety is real; the CPO pairing is the right rep,
>   don't drop it. You still owe him the Marco retro (slipping 2 weeks now — close it Monday).
> - **Managing up:** Sam should hear the inbox scope decision *before* the CPO sync — frame it as
>   on-time delivery (their currency). No surprises.
> - **Decisions:** the v1 scope call is logged, revisit Aug 1. Nothing else to grade yet.
> - **Pattern:** you keep deferring the Marco retro — the one interpersonal-friction item among a week
>   of shipping items. Worth asking why.
> - **Top 3 next week:** (1) close the Marco retro; (2) pair with Alex on the CPO pre-read; (3) send Sam
>   the inbox decision pre-read.
> **The one thing:** get the Marco retro done — it's the thread you keep dropping.

---

## What just happened

Across the day, you spent maybe **five minutes** on capture — a scratchpad dump and four answers — and
got: a ready 1:1, a current dossier, a logged decision you can grade later, an evidence locker entry for
review season, and a weekend-proof read of where your world stands. None of it relied on you *remembering*
to maintain anything; the rituals carried it.

That's the whole idea. See [SKILLS.md](SKILLS.md) for each skill in detail, or [FAQ.md](FAQ.md) for what
happens when things don't go this smoothly.
