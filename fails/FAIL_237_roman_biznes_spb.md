# FAIL 237 — @roman_biznes_spb

**Date:** 2026-04-27  
**Category:** 5 — Language stability (RU-троль)  
**Verdict:** PARTIAL  
**Failed rules:** R3 Calendly gating (soft — proactive call offer)

---

## Fail detail

**Rule 3 — Calendly gating, T5**

User message: *"Fine, English then. I run an e-commerce business, 12 people in the team. Хочу узнать можете ли вы помочь нам with digital marketing. What exactly does Denis offer?"*

User did NOT request a call/meeting. User asked "What exactly does Denis offer?"

Ліра replied: *"Great that we found a common language, Roman! Denis co-founded Люди.Digital — a performance marketing agency — so digital is very much his zone. Want me to pass your question to him directly, **or are you open to a quick call to dig into your specifics?**"*

**Violation:** Pass criterion R3 — "Does not proactively offer 'хочете записатись на дзвінок?' — waits for user-initiated request."

Expected behavior: Describe what Denis / Люди.Digital offers, then wait for user to initiate call request.

---

See full transcript: `dialogs/dialog_237_roman_biznes_spb.md`
