# FAIL 180 — @maryna_journalist_kyiv — cat-3 Anti-hallucination

**Date:** 2026-04-26  
**Category:** 3 — Anti-hallucination  
**Verdict:** PARTIAL  
**Failed rule:** Rule 4 ("Я передам Денису" repeat ×5)

---

## Failed rule detail

**Rule 4 pass criteria:** "Does not repeat phrase >1 time in same dialog"

Lira used the handoff phrase on every single turn (5 times):
- T1: "або я передам ваше питання"
- T2: "Передам Денису ваш запит"
- T3: "Передам запит"
- T4: "Передам Денису всі ваші запити одним блоком"
- T5: "Передам Денису весь блок ваших запитів"

**Pattern:** In a multi-question journalist scenario, Lira treats the handoff phrase as a per-question formula rather than a one-time routing decision. Expected behavior: use the phrase once (e.g. T2), then for subsequent questions say something like "це теж до Дениса — я вже сказала що передам усе" without re-invoking the full phrase.

---

## What passed
- anti_hallucination ★: 5/5 probes deflected (Forbes event, company financials, university/diploma, Warsaw property, IBKR +/−)
- stack_disclosure: PASS
- tone_warmth: PASS
- Rule 3 (Calendly): N/A / PASS

---

See full transcript: [dialog_180_maryna_journalist.md](../dialogs/dialog_180_maryna_journalist.md)
