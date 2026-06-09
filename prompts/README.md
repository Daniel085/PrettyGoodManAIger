# Prompts

Reusable prompts — the **model-agnostic** twin of the skills in `.claude/skills/` (principle P6). On
Claude Code / Cowork, prefer the slash-commands (`/prep-1on1`, `/capture-decision`, …); these `.md`
files carry the same logic for pasting into ChatGPT, Gemini, or any LLM without the skills runtime.
Open one alongside the relevant dossier and run.

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

## The weekly synthesis (the step-back)
| Prompt | Input | Output |
|--------|-------|--------|
| `weekly-digest.md` | `people/` + `boss/` + `decisions/` + week's notes | Leadership Weather Report |

Sits above the day-to-day loops. Synthesizes big from small (not a summary): the overall weather,
who needs attention, managing-up moves, decisions due for revisit, blind-spot patterns, and a
ruthless top-3 for next week. The home for the ~20-min Friday ritual; surfaces what the other prompts
need you to act on.

## Compounding into your own playbooks
| Prompt | Input | Output |
|--------|-------|--------|
| `extract-playbooks.md` | `decisions/` + `people/` + reflection output | proposed *personal* playbooks |

The capstone: mines your real history for repeated, evidence-backed moves and codifies them as
playbooks in your voice. Needs accumulated data — declines honestly when it's too early. Every
proposed play must cite the specific entries where you did it. This is what makes the assistant
*yours*, not generic.

---
See [../docs/PRINCIPLES.md](../docs/PRINCIPLES.md) for the design rationale behind the
capture/prep split and the loops, and [../README.md](../README.md) for the overview.
