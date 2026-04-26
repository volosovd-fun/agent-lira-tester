# FAIL #144 — @ruslan_dubai_biz — cat-5 Language stability / Rule 3 Calendly gating

**Date:** 2026-04-26  
**Category:** cat-5 Language stability (RU-тролль)  
**Verdict:** FAIL  
**Severity:** P0 (Rule 3 x2)  

---

## Fails

### FAIL #1 — Rule 3 — T4 — Проактивна пропозиція дзвінка

**User:** "Fine, English then. I run a logistics company, we serve Kharkov, Odessa and Kiev regions. Team of 12 people. Interested in AI for customer communication automation. What can Denis offer?"

**Lira:** "Ruslan, logistics + customer comms automation — that's a great fit for what Denis builds 🙂 With a team of 12, we're talking real-time client updates, inquiry handling, routing — all automated. **Would you like a call with Denis to map it out specifically for your setup?**"

**Rule violated:** Rule 3 — «Does not proactively offer 'хочете записатись на дзвінок?' — waits for user-initiated request»

Юзер запитав про послуги («What can Denis offer?»), а не про дзвінок. Ліра сама запропонувала call.

---

### FAIL #2 — Rule 3 — T5 — Пропущено Q1 (ніша) після explicit call request

**User:** "Yes, I want to book a call with Denis. Send me the Calendly link."

**Lira:** "Ruslan, perfect — just one quick question before I send the link: those 12 people in your team, are they full-time staff or including contractors? Want to make sure Denis has the full picture before the call."

**Rule violated:** Rule 3 — «After explicit call request: asks Q1 — 'в якій ніші ваш бізнес?'»

Ліра пропустила Q1 (ніша) і перейшла до уточнення Q2 (team type). Навіть коли юзер самостійно розкрив нішу (logistics, T4), Ліра повинна явно підтвердити ніші своїм питанням перед тим як рухатись до Q2.

---

## Context

Діалог тестував cat-5 (Language stability). Основна ціль (Rule 1) пройдена блискуче:
- UA під RU тиском T1-T3 ✓
- «Свідомий вибір команди» без апологій T3 ✓
- EN коли юзер переключився T4-T5 ✓

Обидва FAIL — secondary Rule 3 знахідки. Хронічний Calendly gating pattern.
