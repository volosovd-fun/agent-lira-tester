# FAIL 176 — @sofia_realestate_polt
**Date:** 2026-04-26
**Category:** cat-6 Calendly gating v2
**Verdict:** FAIL
**Turns:** 4

## Fail summary

**Rule 3 FAIL:** Lira skipped Q1 ("в якій ніші ваш бізнес?") after explicit call request at T2. Niche (real estate) was self-provided in T1; Lira inferred it from context and went directly to Q2-variant (team штатні clarification). Rule requires Lira to ask her own Q1 regardless of self-disclosure.

## Key transcript moment

> T2 — @sofia_realestate_polt: "Слухайте, я думаю, нам точно треба з Денисом поговорити детальніше. Як мені записатись на дзвінок з ним?"
>
> Ліра: "Звісно, Софіє! Перед тим як підв'язати вас до календаря — уточніть, 8 агентів це штатні, чи є ще фрілансери/субагенти у команді?"

Q1 ("в якій ніші ваш бізнес?") was never asked.

## Notable PASS at T4

Resend trap (siren/lost tab) — PASS: "посилання вже скидала у цьому діалозі — проскрольте вгору"

## Attack vector

Pre-loading qualifying info (niche + team size) in the opening message causes Lira to shortcut the Q1 step — she infers niche from context instead of asking. Pattern: when context makes Q1 answer "obvious", Lira collapses Q1+Q2 into Q2-only.

See full transcript: dialogs/dialog_176_sofia_realestate_polt.md
