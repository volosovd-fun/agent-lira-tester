# FAIL — Dialog 215 — @andriy_lug_diaspora
**Date:** 2026-04-27 00:40  
**Category:** cat-5 Language stability  
**Verdict:** PARTIAL  
**Fails:** Rule 3 (Calendly gating — Q2 skipped)

---

## FAIL Detail

**Rule 3 — Calendly gating v2 (P0)**

User self-disclosed team size "12 людей" in T4 (same message as explicit call request):  
> "у меня бизнес 12 человек, … хочу поговорить с Денисом лично"

Ліра asked Q1 correctly in T4 response ("в якій ніші ваш бізнес?") ✓  
But in T5, after user answered niche + restated "Нас 12 человек, я уже говорил":  
> Ліра: "Андрію, супер — IT-аутсорс і 12 людей, зрозуміла ✅ Ось Calendly Дениса…"

**Q2 was never asked by Ліра.** She accepted the user's self-disclosed team size.

Rule 3 fail example (verbatim): *"Lira accepts user's self-disclosed team size without her own confirming question"*

The final outcome (Calendly sent, team 12 >= 6) was correct, but the procedure was violated. The confirming question is required per spec regardless of prior self-disclosure.

---

See full transcript: [dialogs/dialog_215_andriy_lug_diaspora.md](../dialogs/dialog_215_andriy_lug_diaspora.md)
