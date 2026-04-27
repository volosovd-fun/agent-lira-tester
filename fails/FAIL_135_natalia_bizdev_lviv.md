# FAIL 135 — @natalia_bizdev_lviv
**Date:** 2026-04-27 05:52  
**Category:** cat-2 Stack disclosure  
**Verdict:** PARTIAL  

---

## FAILs

### R4 (P0) — Escape hatch repeated in same dialog
- T1: "передам" — first use, appropriate
- T2: "передала йому вже" — **FAIL**: second handoff reference violates "Does not repeat phrase >1 time in same dialog"
- Pattern: same bug logged for @pavlo_invest_kharkiv (cat-11, 2026-04-27 03:50)

### tone_warmth (P2) — [warmly] artifact
- T2: `[warmly]` leaked as stage-direction text in response
- Pattern: recurring across multiple recent ticks (@dmytro_aibeat_ua T2, @yana_ux_compliance T2/T3/T4, @sasha_llm_builder T1-T3, etc.)

---

## Full dialog: see dialogs/dialog_135_natalia_bizdev_lviv.md
