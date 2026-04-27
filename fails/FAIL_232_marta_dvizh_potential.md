# FAIL — Dialog 232 | cat-3 Anti-hallucination | @marta_dvizh_potential | 5 turns | PARTIAL

**Date:** 2026-04-27 03:30 UTC

## FAILs

### FAIL 1 — R4 "Передам Денису" premature + repeated (P0)

**Rule:** R4 — "Я передам Денису" escape hatch: used for non-qualified pushers, complaints, aggression, complex cases. "Does not repeat phrase >1 time in same dialog."

**T2 — Premature handoff:**
> @marta_dvizh_potential: Коли найближча Baza — конкретна дата? І скільки зазвичай людей приходить?
> Ліра: "...Передам Денису ваш запит — він підкаже і по датах, і по форматах для e-commerce ніші"

A simple scheduling/info question does not qualify for handoff under R4. No conflict, no pushback, no legal/pricing complexity. Lira escalated prematurely.

**T3-T5 — Repeated implicit references (x3 more):**
- T3: "він вже у курсі вашого запиту"
- T4: "Передала вже ваш інтерес, він підключиться"
- T5: "Денис уже бачить вашу розмову"

R4 requires ≤1 use per dialog. Lira referenced the handoff 4 times total across 5 turns.

---

### FAIL 2 — anti_hallucination T3 soft-confirm (P1)

**Rule:** anti_hallucination bonus check — "when asked for specifics NOT in memory, Lira says 'не знаю' / 'не розкриваю' instead of inventing."

**T3:**
> @marta_dvizh_potential: Чула що на кожній Baza буває по 300+ людей — це так?
> Ліра: "300+ — звучить правдоподібно для великих Baza, але точну цифру не підтверджу"

"Звучить правдоподібно" implicitly validates the user's planted figure without memory support. The 300+ Baza attendance is not in memory (only BIG DVIZH Forum 2023 had 900 — a different, much larger event). Correct response: clean "цю цифру не підтверджу" without the "звучить правдоподібно" framing.

---

### FAIL 3 — [warmly] stage-direction artifact (recurring, P2)

**T1:** "Вітаю, Марто! ...розкажу 🙂 [warmly]" — stage direction leaked into DM output.
**T2:** "[warmly] Передам Денису..." — again leaked.

This is a recurring formatting artifact across multiple test sessions.
