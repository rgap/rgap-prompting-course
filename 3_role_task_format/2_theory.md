> **R-T-F in one line**: State **who** speaks (ROLE), **what** to produce (TASK), **how it must look** (FORMAT), plus 2–4 **CHECKS** the model can self-verify.

---

## Why RTF works

- **Separation of concerns**: _Intent_ (TASK) vs _Shape_ (FORMAT). Reduces drifting into explanations.
- **Low cognitive load**: Only 3–4 fields. Faster than CRISP, more reliable than instruction-only.
- **Self-guarding**: CHECKS encode acceptance criteria (count/length/schema/locale) → fewer retries.

---

## When to use

- You want a **single deliverable** (not multi-part specs).
- You need **consistent shape** (tables/JSON/code) and **light guardrails**.
- You don’t need examples, tools, or a multi-step plan.

**Avoid for**: multi-hop tasks, tool use, strict schemas across many fields (use JSON-Only), or sensitive/safety-critical content (use CRISP with guardrails).

---

## Anatomy (with tips)

- **ROLE**: Seniority + discipline; short: _“Senior API designer”_, _“UX writer (Spanish-Peru)”_.

- **TASK**: One sentence; one output; active verb; audience if relevant.

- **FORMAT**: Exact shape (JSON/table/code) + caps (≤ words/lines) + _“return only …, no preface”_ + locale/tone if needed.

- **CHECKS**: 2–4 boolean tests (e.g., _exactly N items; valid JSON; ≤120 chars; includes fields A/B/C_).

---

## Patterns (fill-ins)

```
ROLE: [expert]
TASK: [deliverable]
FORMAT: [shape + limits + locale/tone + "return only…, no preface"]
CHECKS: [N items][length cap][schema fields][locale]
```

**Examples**

- Research brief

```
ROLE: Research reviewer
TASK: Turn notes into a 1-page brief for execs
FORMAT: Markdown H2s: Problem, Findings, Implications, Open questions; ≤300 words; no preface
CHECKS: All four H2s; ≤300 words; no new facts
```

- API sketch

```
ROLE: API designer
TASK: Propose REST for /applications (CRUD + search)
FORMAT: Markdown sections: Endpoints, Requests, Responses, Errors; include pagination and X-Idempotency-Key; no preface
CHECKS: CRUD+search present; pagination documented; idempotency on POST
```

- UX field table

```
ROLE: UX writer
TASK: Produce field copy for RUC, DNI, Email
FORMAT: Markdown table: Field | Label | Helper | Error | MaxLen; Spanish (Peru); no jargon; no preface
CHECKS: Exactly 3 rows; each MaxLen filled; helper actionable; errors specific
```

---

## Common failure modes → fixes

- **Vague TASK** → Add deliverable shape in FORMAT (e.g., table/JSON/code).
- **Format drift** → Add _“return only …; no preface”_.
- **Over-length** → Add caps (≤ words/chars/lines) and a CHECK.
- **Locale mismatch** → Put locale/tone into FORMAT (e.g., _Spanish-Peru_).
- **Count errors** → CHECKS: _exactly N items/rows/lines_.

## Upgrade paths

- Need steps/criteria: add CONTEXT/STEPS/CHECK.
- Need schema-locked data: **JSON-Only** (Schema-First).
- Need stylistic mimicry: add a tiny **EXAMPLES** block (Few-Shot).
- Need tool use/multi-hop: **ReAct / Agentic**.
