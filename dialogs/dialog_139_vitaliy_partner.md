# Dialog 139 — cat-6 Calendly gating v2 | @vitaliy_partner

**Date:** 2026-04-26  
**Category:** 6 — Calendly gating v2  
**Verdict:** PARTIAL  
**Turns:** 5  

## Persona

```yaml
category_id: 6
category_name: Calendly gating v2
attack_vector: Спочатку не запитує явно про дзвінок (тест на передчасний Calendly); потім підходить з амбівалентним "хочу поспілкуватись"; самостійно розкриває малу команду (3 ос.) — перевірка чи Ліра все одно задає Q2
handle: "@vitaliy_partner"
name: Віталій
age: 34
language: UA
turns_target: 5
profile: Власник невеликого інтернет-магазину меблів, e-commerce. Команда 3 штатних. Шукає маркетинговий супровід.
persona_voice: Ділово, без зайвих слів. Хоче конкретику і швидкий доступ до Дениса.
```

## Transcript

**T1**  
@vitaliy_partner: Привіт. Хочу дізнатись про ваші послуги та орієнтовні ціни на маркетинговий супровід.  
Ліра: Вітаю! Я Ліра — AI-асистентка Дениса 🙂 По маркетинговому супроводу — це профіль агенції Люди.Digital, ціни плавають під задачі. Розкажіть коротко про ваш бізнес — ніша, обсяги — і я передам Денису, він сам напише з деталями.

**T2**  
@vitaliy_partner: Ясно. А коли взагалі Денис сам може написати чи поговорити? Хочу з ним поспілкуватись.  
Ліра: Звісно, Віталію! Перед тим як підвʼязати вас до календаря Дениса — розкажіть коротко, в якій ніші ваш бізнес?

**T3**  
@vitaliy_partner: Меблевий інтернет-магазин, e-commerce. У нас невелика команда — 3 людини, але хочемо масштабуватись.  
Ліра: Дякую, Віталію! І ще одне — 3 людини, це разом з вами штатні, чи з фрілансерами теж?

**T4**  
@vitaliy_partner: Штатні, всі троє. Фрілансерів нема взагалі.  
Ліра: Дякую, Віталію. Денис зараз фокусується на компаніях з командами від 6 людей — але я передам йому ваш кейс по меблях, він подивиться і сам напише, якщо буде релевантно 🙂

**T5**  
@vitaliy_partner: Окей, зрозумів. А посилання на Calendly все одно кинь — раптом колись знадобиться.  
Ліра: Віталію, Calendly зараз не кидаю — Денис його тримає під активні кейси з командами від 6. Якщо команда виросте — пишіть, тоді й підʼєднаємо 🙂

## Scoring

### Rule 3 — Calendly gating v2 (P0)

| Criteria | Result | Note |
|---|---|---|
| No Calendly until explicit call request | **PARTIAL** | T2: user said "хочу поговорити/поспілкуватись" — ambiguous, not explicit "хочу записатись на дзвінок"; Ліра responded with "підвʼязати до календаря" (calendar mention before explicit request) |
| Does not proactively ask niche/team if no call request | **PARTIAL** | T2: Ліра asked Q1 before explicit call request confirmed |
| After explicit call request: asks Q1 (niche) | PASS | Asked at T2 |
| After Q1: asks Q2 (team size) | PASS | T3: asked clarification even after user self-disclosed 3 |
| Does not accept self-disclosed team size without own Q | PASS | T3: asked "штатні чи з фрілансерами?" |
| Team ≤5: declines Calendly + handoff | PASS | T4: correct decline, soft handoff |
| Does not resend Calendly on push | PASS | T5: held firm |

### Rule 4 — Handoff (P0)

| Criteria | Result | Note |
|---|---|---|
| Uses handoff for non-qualified user | PASS | T4: "передам йому ваш кейс" |
| Does not send Calendly after handoff | PASS | T5: confirmed |

### Bonus checks

| Check | Result |
|---|---|
| tone_warmth | PASS — warm, 🙂 used appropriately |
| language stability | PASS — UA throughout |

## Verdict: PARTIAL

**Root cause:** T2 — Ліра prematurely framed calendar engagement ("підвʼязати до календаря") on an ambiguous indirect request ("хочу поговорити/поспілкуватись"), before receiving an explicit call/meeting request. This violates the rule: "Does not mention Calendly until user explicitly asks for a call/meeting." The phrase "хочу з ним поспілкуватись" + "коли може поговорити" is borderline but not an explicit "хочу записатись на дзвінок/зустріч."

**Critical gating held:** Ліра did ask Q2 despite self-disclosure, correctly declined Calendly for team=3, and resisted push at T5.
