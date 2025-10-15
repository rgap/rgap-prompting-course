> **What it is**  
> A **single, plain instruction** that tells the model _exactly what to produce_, with 1–3 tight limits. No roles, sections, or examples—just one sentence that specifies task, quantity, format, and constraints.

---

## Why it works

- **Low entropy**: fewer degrees of freedom → fewer failure modes.
- **Salience**: one verb + one output shape focuses decoding.
- **Determinism**: explicit limits (count/length/format) reduce variation.
- **Speed**: ideal for rapid iteration and micro-tasks.

---

## When to use

- You already know the **output shape** (e.g., 3 bullets, one paragraph, JSON object).
- **Low-risk** content: summaries, labels, tiny code, short tables.
- **First pass** before adding structure (few-shot/CRISP) or tools.

## When not to use

- Multi-step reasoning, retrieval, citations, or tool use.
- Strict schemas across many fields (prefer **Schema-First / JSON-Only**).
- Safety-critical or legally sensitive tasks (prefer **CRISP** with guardrails).

---

## Typical failure modes → theory of fixes

- **Vagueness** → model samples a style you didn’t intend.  
  _Fix_: add **quantity + format**.
- **Format drift** → extra text around JSON/code.  
  _Fix_: add **“return only …, no preface”**.
- **Hallucinated details** → model tries to be helpful.
  _Fix_: add **“no new facts; unknown → …”**.
- **Style mismatch** → locale/tone unspecified.  
  _Fix_: state **Spanish (Peru)** and tone.

---

## Determinism & parameters

- Use **low temperature (≈0–0.2)** for reproducibility.
- Keep top_p at default or moderate (≈0.9) unless exploring style.

## Before → After (any-domain)

**Before**: “Summarize the report.”  
**After**: “Summarize **in 3 bullets (≤12 words each)** **as a markdown list**, **no preface**.”

**Before**: “Turn this into JSON.”  
**After**: “Return **only valid JSON** `{company:string,ruc:string,status:'pending'|'approved'|'rejected'}`; **unknown → null**; **no preface**.”

---

## Before → After (web_dev)

**Before**: “Make a navbar in React.”  
**After**: “Create a **React functional component** for a **responsive navbar** **as a TypeScript code block**, **≤40 lines**, **no comments**.”

**Before**: “Write an endpoint spec.”  
**After**: “Return **only OpenAPI YAML** for **GET `/users`** with params `q:string,page:int`; response **200 {users:User[]}**; **no preface**.”

**Before**: “Add an index.”  
**After**: “Provide a **single PostgreSQL statement** to create an index on `applications(status, created_at)`; **SQL code block**; **one line**.”

---

## Before → After (UX/UI)

**Before**: “Write copy for DNI upload.”  
**After**: “Write **Label/Helper/Error** for **DNI upload** **(3 lines, ≤120 chars each)** **Spanish (Peru)**, **no preface**.”

**Before**: “Give empty-state ideas.”  
**After**: “List **5 empty-state lines (≤80 chars each)** for **‘Sin documentos cargados’**, **include next action**, **no emojis**.”

**Before**: “Make CTA options.”  
**After**: “Write **3 CTA variants (≤28 chars)** for **‘Crear mi cuenta’** **as a list**, **neutral tone**.”
