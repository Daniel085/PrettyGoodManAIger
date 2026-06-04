# Prompts

Reusable prompts. Each is platform-agnostic markdown — open it alongside the relevant dossier in
Claude / Cowork and run.

## The reports loop (managing down)
| Prompt | Input | Output |
|--------|-------|--------|
| `capture-post-1on1.md` | raw 1:1 notes + report dossier | proposed dossier edits to approve |
| `prep-1on1.md` | report dossier (+ playbooks) | 60-second pre-meeting brief |

**The loop:** prep → have the 1:1 → capture → (dossier gets richer) → better prep next time.
That compounding is the whole point: the brain gets smarter as you lead.

## The managing-up loop
| Prompt | Input | Output |
|--------|-------|--------|
| `build-boss-profile.md` | Gmail/Slack connectors (default) or pasted comms | draft boss dossier |
| `prep-boss-1on1.md` | boss dossier + managing-up playbooks | decision-room 1:1 brief |

`build-boss-profile.md` defaults to pulling from your email/Slack connectors and falls back to paste.
Grounded in Gabarro & Kotter (mutual dependence), Cohen & Bradford (currencies), Neffinger & Kohut
(strength × warmth) — see `templates/boss-dossier-template.md` and the docs.

## The decision log (the reflection loop)
| Prompt | Input | Output |
|--------|-------|--------|
| `capture-decision.md` | a judgment call, in ~60 sec | a frozen decision file in `decisions/` |
| `reflect-on-decisions.md` | `decisions/` (due or in bulk) | graded verdicts + patterns + playbook candidates |

Log calls *before* you know the outcome; revisit later to grade your judgment honestly (defeats
hindsight bias). Pattern review across many decisions is the feedstock for extracting *your* own
playbooks. Decision-journal logic (Kahneman; Duke, *Thinking in Bets*) + ADR structure.

## Coming next
- Weekly digest / "Leadership Weather Report" (incl. surfacing decisions due for revisit)
- Playbook extraction (mine the decision log + captures → propose *your* playbooks) — partly enabled
  by `reflect-on-decisions.md` pattern review

---
See [../docs/PRINCIPLES.md](../docs/PRINCIPLES.md) for the design rationale behind the
capture/prep split and the two loops, and [../README.md](../README.md) for the overview.
