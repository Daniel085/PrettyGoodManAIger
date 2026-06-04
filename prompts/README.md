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

## Coming next
- Weekly digest / "Leadership Weather Report"
- Decision log + outcome loops (revisit past calls — was my judgment right?)
- Playbook extraction (mine the decision log + captures → propose *your* playbooks)

---
See [../docs/PRINCIPLES.md](../docs/PRINCIPLES.md) for the design rationale behind the
capture/prep split and the two loops, and [../README.md](../README.md) for the overview.
