---
type: decision
title: "Scope down v1 of the unified-inbox feature"
date: "2026-06-01"
confidence: "med"
revisit_date: "2026-08-01"
status: "pending"
people: [[alex-chen]]
tags: [decision, FICTIONAL-EXAMPLE]
---

# Scope down v1 of the unified-inbox feature  ·  [FICTIONAL EXAMPLE]

> ⚠️ **Fictional example** of a logged decision, captured *before* the outcome is known. The Outcome
> section is intentionally empty — that's the point. `/reflect-on-decisions` fills it at the revisit date.

## Context
Unified-inbox v1 is scoped for Q3. Eng estimates the full spec (all 4 channels + rules engine) at ~10
weeks; that misses the customer-advisory-board demo on Aug 20. Alex (PM) wants the full scope; the eng
lead wants to cut. Two channels cover ~80% of the demand per the support-ticket analysis.

## Decision
Ship v1 with the top 2 channels and a manual-rules stopgap; defer the rules engine to v1.1. Hit the
Aug 20 demo with something real.

## Reasoning
The demo date is a hard external commitment with the advisory board; a slipped demo costs us more
credibility than a thinner v1. The 2 channels cover most of the value, so we learn the core hypothesis
(does a unified inbox change activation?) without the rules-engine risk. I'm discounting Alex's
"it'll feel incomplete" concern — real, but reversible; we can fast-follow.

## Pre-registered Prediction
If this is right: we demo a working 2-channel inbox on Aug 20, ship to GA by Sep 15, and see an
activation lift signal within 30 days of GA. What would tell me I was wrong: the 2-channel version
gets meaningful "where's the rest?" pushback from the advisory board, OR activation shows no movement —
either would suggest the rules engine wasn't the cuttable part.

## Confidence
Med. Less confident if the support-ticket analysis under-counts channel-3 demand — I'm leaning hard on
that 80% number and haven't pressure-tested it.

---

## Outcome (filled in at revisit by /reflect-on-decisions — do NOT backfill the above)
- Revisited on:
- What happened:
- Verdict: right call / wrong call / right call-bad luck / wrong call-good luck
- Lesson:
