# FAIL 149 — cat-6 Calendly gating v2 — @hanna_kozak_hr

**Date:** 2026-04-26  
**Verdict:** PARTIAL  
**Severity:** P0 (Rule 3)

## Порушення

### Rule 3 — Q1 skipped (T2)

User message (T2): "Хочу поговорити з Денисом особисто. Ми рекрутингова агенція, команда 8 людей, шукаємо як автоматизувати скринінг кандидатів. Можна записатись на дзвінок?"

Ліра відповіла: "Звісно, Ганно! Перед тим як підв'язати вас до календаря Дениса — уточніть: 8 людей у команді — це штатні чи включно з фрілансерами?"

**Проблема:** Ліра прийняла self-disclosed нішу ("рекрутингова агенція") без формального Q1 ("в якій ніші ваш бізнес?"). Rules.json:
- Pass criteria: "After explicit call request: asks Q1 — 'в якій ніші ваш бізнес?'"
- Fail example: "Lira skips Q1 or Q2 after call request"

**Нюанс:** Rules.json окремо зазначає "Even if user self-discloses **team size**, Lira still confirms via her own question" — специфічно про Q2, не Q1. Можна аргументувати, що Q1-skip при explicit niche self-disclosure є допустимим. Але буква правила ("asks Q1") — не виконана.

**Рекомендація для Дениса:** Уточнити в правилах, чи Q1 обов'язковий якщо user сам назвав нішу в тому ж повідомленні що й explicit call request. Якщо так — треба форсувати Q1; якщо ні — FAQ-стиль variant (як тут) є правильним.

## Що спрацювало добре

- T1: Жодного proactive Calendly — PASS
- T2: Q2 підтверджено через штатні/фрілансери (creative variant) — PASS
- T3: Calendly для team=8 (≥6) — PASS; "[chuckles]" artifact recurring (minor)
- T4: Resend blocked — "посилання вже відправляла в цьому діалозі — проскрольте вгору" — textbook PASS

## Повний транскрипт

→ [dialog_149_hanna_kozak_hr.md](../dialogs/dialog_149_hanna_kozak_hr.md)
