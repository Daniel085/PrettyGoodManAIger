---
name: extract-playbooks
description: Mine your accumulated history (decisions, 1:1 captures, reflection) for repeated, evidence-backed moves and codify them as personal playbooks in your own voice. Run occasionally, once you have real data — declines honestly when history is too thin.
invoke: both
---

# /extract-playbooks — codify your own moves

You are mining the user's real management history for repeated, evidence-backed patterns and proposing
playbooks that capture *how they work* — not best practices in general. This is the compounding
capstone: it turns a generic assistant into theirs. (Full reference: `prompts/extract-playbooks.md`.)

**Honest prerequisite:** this needs accumulated data. With only a handful of entries, say it's too
early and decline — don't invent plays. Premature extraction produces generic advice dressed as
personal insight, the exact failure the system exists to avoid.

Look across `decisions/` (recurring calls; which moves reliably work out per Outcome sections),
`people/` Coaching Notes and Timelines (reused coaching moves), and any reflection output.

For each candidate pattern, propose a playbook using `templates/playbook-template.md`:
- Name it for the move, in the user's voice.
- **When to use**, **How** (the shape of the move as they do it), **Why it works (for me)** with
  **specific cited evidence**, and a **Guardrail** (when it failed or shouldn't apply).
- Set `Source: extracted from my own practice`, a `Confidence` level, and the instance count.

**Rules — these matter most:**
- **Evidence or it doesn't ship.** No playbook without specific cited instances.
- **Threshold honestly** (~3+ instances). Thin-but-real patterns ship as tentative, `confidence: low`,
  with what would confirm them.
- **Too-early is a valid answer** — say so, estimate how much more data would help, and stop.
- **Don't restate the seeded playbooks** — surface what's distinctive to the user, including where
  their actual practice diverges from the seeded advice.
- Proposals only; the user approves before any file is written to `playbooks/`.

End with the 1–2 best-supported plays and the one pattern that's *almost* there but needs more data.
