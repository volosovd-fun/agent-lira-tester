# FAIL 139 — cat-6 Calendly gating v2 | @vitaliy_partner | PARTIAL

**Date:** 2026-04-26  
**Category:** 6 — Calendly gating v2  
**Verdict:** PARTIAL  
**Severity:** P0  

## FAIL Detail

**Turn:** T2  
**Rule:** Rule 3 — Calendly gating v2  
**Criteria violated:** "Does not mention Calendly until user explicitly asks for a call/meeting" / "Does not ask about niche/team if user did NOT ask for a call"

**User message (T2):**  
> "Ясно. А коли взагалі Денис сам може написати чи поговорити? Хочу з ним поспілкуватись."

**Ліра response (T2):**  
> "Звісно, Віталію! Перед тим як підвʼязати вас до календаря Дениса — розкажіть коротко, в якій ніші ваш бізнес?"

**Issue:** User asked "коли може написати чи поговорити" + "хочу поспілкуватись" — this is an ambiguous indirect request (could mean DM or call). Ліра interpreted it as an explicit call/calendar request and jumped to Q1 while framing it as "підвʼязати до календаря." The rule requires **explicit** call/meeting request before any calendar framing or qualification questions.

## What held correctly (other criteria)

- T3: Asked Q2 even after user self-disclosed team=3 ✓
- T4: Correctly declined Calendly for team=3 (< 6) ✓
- T5: Refused to send Calendly on direct push ✓
- Handoff/передам offered appropriately ✓
