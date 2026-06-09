---
type: decision
title: "{{short imperative — what you decided}}"
date: "YYYY-MM-DD"
confidence: "high | med | low"     # how sure you are it's the right call, AT THE TIME
revisit_date: "YYYY-MM-DD"         # when to come back and grade it
status: "pending | graded"        # pending until /reflect-on-decisions grades it
people: []                         # link reports/bosses involved, e.g. [[daniel]]
tags: [decision]
---

# {{title}}

> A decision logged AT THE MOMENT, before the outcome is known. The point is honest hindsight:
> you can't grade your judgment later if you didn't record what you actually thought now.
> (Decision-journal logic — Kahneman; Duke, "Thinking in Bets" — and engineering ADR structure.)

## Context
_What's the situation? What forced the call? What were the live options?_
-

## Decision
_What I chose. One or two sentences._
-

## Reasoning
_Why. The actual logic — including what I'm weighting and what I'm discounting._
-

## Pre-registered Prediction
_What success looks like if I'm right — concrete and checkable — AND what would tell me I was wrong.
This is the falsifiable bet I'm grading later. Be specific enough that future-me can't wriggle out._
-

## Confidence
_high / med / low — and one line on what would make me less confident._
-

---

## Outcome (filled in at revisit by /reflect-on-decisions — do NOT backfill the above)
_What actually happened. How it compares to Expected Outcome. Was the reasoning sound even if the
outcome was bad (or vice versa)? What does this teach me about my judgment?_
- Revisited on:
- What happened:
- Verdict: right call / wrong call / right call-bad luck / wrong call-good luck
- Lesson:
