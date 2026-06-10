---
type: decision
title: "Scope down v1 of the unified-inbox feature"
date: "2026-06-01"
confidence: "med"
revisit_date: "2026-08-01"
status: "pending"
people: [[alex-chen]]
tags: [decision, FICTIONAL-DEMO]
---

# Scope down v1 of the unified-inbox feature  ·  (fictional demo)

## Context
Full spec (4 channels + rules engine) estimated ~10 weeks — misses the Aug 20 advisory-board demo. Alex
wanted full scope; Marco's team wanted to cut. Support-ticket analysis says 2 channels cover ~80% of
demand.

## Decision
Ship v1 with the top 2 channels + a manual-rules stopgap; defer the rules engine to v1.1. Hit Aug 20.

## Reasoning
The demo date is a hard external commitment; a slipped demo costs more credibility than a thinner v1.
Two channels test the core hypothesis (does a unified inbox move activation?). Discounting Alex's
"feels incomplete" concern — real but reversible. Leaning hard on the 80% ticket analysis.

## Pre-registered Prediction
If right: demo a working 2-channel inbox Aug 20, GA by Sep 15, activation lift signal within 30 days of
GA. Wrong if: meaningful "where's the rest?" pushback from the advisory board, OR no activation
movement — either says the rules engine wasn't the cuttable part.

## Confidence
Med (~70%). Less confident if the ticket analysis under-counts channel-3 demand — haven't
pressure-tested that number.

---

## Outcome (filled in at revisit by /reflect-on-decisions — do NOT backfill the above)
- Revisited on:
- What happened:
- Verdict: right call / wrong call / right call-bad luck / wrong call-good luck
- Lesson:
