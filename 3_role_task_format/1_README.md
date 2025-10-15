# Role–Task–Format (03) — README.md

> **What it is**
> A tiny structured prompt: **ROLE · TASK · FORMAT · CHECKS**. Lighter than CRISP, heavier than one-line. Great default when you want speed with minimal guardrails.

---

## Minimal template (copy/paste)

```
ROLE: [expert to emulate]
TASK: [what to produce; single objective]
FORMAT: [exact output shape: JSON/markdown table/code block + limits]
CHECKS: [2–4 acceptance criteria: count/length/schema/locale]
```

### Tips

- Keep **TASK** to one sentence and one deliverable.
- In **FORMAT**, say “**return only …, no preface**”.
- Put locale/tone in **FORMAT** or **CHECKS** (e.g., “Spanish-Peru”).
- Use **CHECKS** for exact counts and length caps.

---

## Any-domain example

```
ROLE: Research reviewer
TASK: Turn the notes into a 1-page brief for execs
FORMAT: Markdown with H2s: Problem, Findings, Implications, Open questions; ≤300 words; no preface
CHECKS: All four H2s present; ≤300 words; no new facts
```

## Web dev example

```
ROLE: API designer
TASK: Propose REST endpoints for /applications (CRUD + search)
FORMAT: Markdown sections: Endpoints, Requests, Responses, Errors; include pagination and X-Idempotency-Key; no preface
CHECKS: Has GET/POST/PUT/DELETE + /search; pagination documented; idempotency on POST
```

## UX/UI example

```
ROLE: UX writer
TASK: Produce field copy for RUC, DNI, Email
FORMAT: Markdown table: Field | Label | Helper | Error | MaxLen; Spanish (Peru); no jargon; no preface
CHECKS: Exactly 3 rows; each MaxLen filled; helper actionable; errors specific
```

---

## Common pitfalls → quick fixes

- **Vague TASK** → Add the single deliverable (“…as a table/code/JSON”).
- **Format drift** → In FORMAT add **“return only …; no preface”**.
- **Missing locale/tone** → Add to FORMAT (“Spanish-Peru, friendly-professional”).
- **Unreliable counts** → In CHECKS add **“exactly N items/rows/lines”**.
- **Overly broad** → Split into two RTF prompts (one per deliverable).
