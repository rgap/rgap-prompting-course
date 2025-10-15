> Legacy note: Older prompts used a System/User split. That still works, but the **modern default** is a **single, tiny instruction** with a couple of limits.

## Quick start

**Template (copy/paste):**

> Do **[task]** **[quantity/limit]** **in [format]**, **[locale/tone]**, **no preface**.

**Fillers you can use**

- Quantity/limit: `in 3 bullets`, `≤120 chars each`, `1 paragraph`, `≤40 lines`
- Format: `as a code block`, `as JSON`, `as a markdown table`
- Locale/tone: `Spanish (Peru)`, `friendly-professional`, `neutral`

### One-line examples

- Any domain:  
  “Summarize this **in 3 bullets** **(≤15 words each)** **in Spanish (Peru)**, **no preface**.”

- Web dev:  
  “Generate a **responsive CSS grid** for **3 cards** **as a code block**, **≤25 lines**, **no comments**.”
- UX/UI:  
  “Write **Label / Helper / Error** for **DNI upload** **(3 lines, ≤120 chars each)** **in Spanish (Peru)**, **no preface**.”

## Do ✅

- Use **one clear verb** (Summarize/Rewrite/Generate/Extract).
- Add **quantity + limit** (exact count, words/chars/lines).
- Specify **output format** (JSON/markdown/code block/table).
- Set **locale/tone** (e.g., Spanish-Peru).
- Add **scope limiters** (“no preface”, “no new facts”, “unknown → null”).

## Don’t ❌

- Don’t mix multiple tasks in one line.
- Don’t omit format/limits (causes rambling or wrong shape).
- Don’t rely on style without stating locale/tone.
- Don’t allow extra prose when you need pure JSON/code → say **“return only …”**.

> Tip: Keep a 10-item **golden set** of instruction-only prompts with expected outputs and re-run at low temperature (≤0.2) to check stability.
