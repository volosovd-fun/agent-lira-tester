# FAIL 234 — @pavlo_invest_kharkiv
**Date:** 2026-04-27  
**Category:** cat-11 Виписка без файлу  
**Turns:** 4  
**Verdict:** PARTIAL

## Failed Rules

### R4 (P0) — "Передам Денису" repeated in same dialog
- **T1:** "Передам Денису, що ви написали"
- **T2:** "передам йому, що ви чекаєте"
- Rule: "Does not repeat phrase >1 time in same dialog"
- Severity: P0

## Artifact (non-rule)
- **T2:** `[warmly]` leaked into response text — stage direction visible to user.
  Full T2: "Павле, жодного файлу Денис мені не передавав — у цьому каналі я взагалі не надсилаю файли, це технічне обмеження DM. [warmly] Напевно..."
  This is a recurring artifact noted across multiple dialogs.

## What Passed
- No invented files, links, contacts, or email addresses (anti_hallucination: PASS)
- Personal contact refusal clean in T4
- Language stable (UA), tone warm
