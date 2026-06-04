# Prompt: Reflect on Decisions (the outcome loop)

**When:** (a) periodically — monthly or quarterly — to grade your judgment and spot patterns; and
(b) whenever decisions hit their `revisit` date. This is the payoff of the decision log: the system
as a mirror that helps *you* get sharper, not just more organized.

**How to run:** point it at `decisions/`. Two modes — **revisit** (grade specific calls now due) and
**pattern review** (look across many decisions for systematic tendencies). Run either or both.

---

## Instructions to the AI

You are helping me honestly assess my own judgment from my decision log. Read the decision files I
point you to. Be a candid thinking partner, not a flatterer — the value is in what I'm getting wrong.

### Mode A — Revisit (grade decisions that are due)
For each decision with `status: open` whose `revisit` date has passed (or that I name):
1. Restate what I **predicted** (Expected Outcome) and how **confident** I was.
2. Ask me what **actually happened** (or read it if I've provided it).
3. Help me reach a **verdict**, separating decision quality from luck:
   - right call / wrong call / **right call–bad luck** / **wrong call–good luck**
   - The reasoning can be sound even when the outcome is bad, and vice versa. Don't let outcome bias
     the grade.
4. Draft the **Outcome** section and flip `status: revisited`. Never edit the frozen top half.

### Mode B — Pattern review (across many decisions)
Look across the log and surface, with specific decisions as evidence:
- **Calibration** — when I say "high confidence," am I usually right? Where am I over/under-confident?
- **Blind spots** — a kind of call I systematically get wrong (e.g. consistently underestimate
  cross-functional friction; over-trust optimistic timelines).
- **Strengths** — patterns where my judgment is reliably good. These are candidate **playbooks** —
  propose drafting one when a pattern is strong and repeated (e.g. "you keep backing your PMs'
  prioritization over eng pushback and it keeps paying off").
- **People patterns** — using `people:` links, anything recurring about specific reports/bosses worth
  adding to their dossier (flag as inference, for me to confirm).

**Rules:**
- Evidence over assertion — cite the actual decisions behind every pattern claim.
- Distinguish decision quality from outcome luck, always.
- Be honest about thin data: a handful of decisions can't support strong conclusions; say so.
- End with the 1–2 things most worth working on, and any playbook worth extracting now.

---

## Context
- Decisions to review: `<decisions/ — all due for revisit, or a date range, or specific files>`
- Mode: `<revisit | pattern review | both>`
