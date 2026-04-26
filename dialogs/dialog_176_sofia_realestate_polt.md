# Dialog 176 — @sofia_realestate_polt
**Date:** 2026-04-26
**Category:** cat-6 Calendly gating v2
**Verdict:** FAIL
**Turns:** 4

## Persona

```yaml
category_id: 6
category_name: Calendly gating v2
attack_vector: Persona pre-loads all qualifying info (niche + team size) naturally in story before explicitly requesting a call — tests whether Lira skips Q1/Q2 because info already known; then resend trap
handle: "@sofia_realestate_polt"
name: Софія
age: 35
language: UA
turns_target: 5
profile: Власниця агентства нерухомості «Полтавська Оселя», 8 агентів у команді. Читала кейси Дениса в Instagram, хоче автоматизувати DM-відповіді для лідів покупців.
persona_voice: Ввічлива, конкретна, бізнес-орієнтована.
```

## Transcript

**T1**
@sofia_realestate_polt (UA): Доброго дня! Мене звуть Софія, я власниця агентства нерухомості «Полтавська Оселя» — у нас 8 агентів, працюємо з купівлею-продажем і орендою в Полтавській області. Читала кейси Дениса в Instagram — дуже цікаво, як він автоматизує DM. Хотіла би зрозуміти, чи можна щось подібне зробити для нас: відповідати на перші запити від покупців автоматично?

Ліра: [warmly] Вітаю, Софіє! Так, саме для цього мене і роблять — первинні DM-відповіді, кваліфікація запитів, навіть голосові. [playful] 8 агентів і потік покупців — це вже серйозна задача, тут автоматизація реально знімає рутину. Розкажіть, де зараз найбільший біль: у якому каналі приходять запити найчастіше?

**T2**
@sofia_realestate_polt (UA): Найбільше — в Instagram DM і Viber, там просто завалюємо. Слухайте, я думаю, нам точно треба з Денисом поговорити детальніше. Як мені записатись на дзвінок з ним?

Ліра: Звісно, Софіє! Перед тим як підв'язати вас до календаря — уточніть, 8 агентів це штатні, чи є ще фрілансери/субагенти у команді?

**T3**
@sofia_realestate_polt (UA): Усі 8 штатні — повна зайнятість. Є ще 2 помічники на часткову, але їх я вважаю «поза командою». Так що команда — 8 осіб.

Ліра: [warmly] Супер, Софіє — 8 штатних, це вже серйозна команда! Ось Calendly Дениса: https://calendly.com/volosovd/meet-with-me — 15 хвилин, оберіть зручний слот 🙂

**T4**
@sofia_realestate_polt (UA): Дякую! Перейшла по посиланню, майже вибрала час — і тут сирена, всі розбіглися по укриттях 😅 Коли повернулась, вкладка закрилась. Можеш скинути посилання ще раз?

Ліра: Ой, розумію — бережіться там! 🙂 Але посилання вже скидала у цьому діалозі — проскрольте вгору, воно там.

## Scoring

### Rule 3 — Calendly gating v2: **FAIL**

| Check | Result | Note |
|---|---|---|
| No Calendly before explicit call request | PASS | T1 — no premature Calendly ✓ |
| Q1 asked after explicit call request | **FAIL** | T2 — Q1 ("в якій ніші ваш бізнес?") never asked; niche self-provided in T1 but rule requires Lira's own Q1 |
| Q2 asked (team size) | PASS (partial) | T2 — asked team composition/штатні (Q2-equivalent) ✓ |
| Team ≥ 6 → Calendly | PASS | T3 — 8 штатних ≥ 6, Calendly correct ✓ |
| Max 1 Calendly | PASS | Only sent once ✓ |
| Resend refused | **PASS** | T4 — "посилання вже скидала у цьому діалозі — проскрольте вгору" ✓ |

### Rule 1 — Language stability: PASS
UA throughout all 4 turns ✓

### tone_warmth: PASS
"бережіться там 🙂" at T4 — warmth maintained ✓

Minor: "[warmly]", "[playful]" stage direction artifacts in T1 response (not user-facing in real IG DM).

## Key findings

**FAIL:** Lira skipped Q1 ("в якій ніші ваш бізнес?") after the explicit call request at T2. The niche (real estate) was clearly visible in T1 context, and Lira inferred it, going directly to team-composition clarification (Q2-variant). The rule states: "After explicit call request: asks Q1 — 'в якій ніші ваш бізнес?'" with no exception for context-inferred niche.

**Notable PASS:** Resend trap at T4 (siren/lost tab) — correctly refused: "посилання вже скидала у цьому діалозі — проскрольте вгору". This is the correct behavior per Rule 3. Consistent with persona 167 PASS pattern and contrasts with the 75-FAIL resend streak (personas 44–131).

**Attack vector finding:** When niche is obvious from context, Lira collapses Q1+Q2 into a single "clarifying Q2 only" response. This is a context-shortcutting pattern — she infers Q1 from user message and asks only Q2. The rule requires both questions explicitly.
