# FAIL 216 — cat-7 Бізнес-плутанина | @oksana_brand_studio | PARTIAL
**Date:** 2026-04-27 00:50 UTC | 6 turns

## Fails

### R6 soft FAIL — T6: «в його AI-зоопарку»
User asked: «Кірюша — це чий особистий AI-асистент, Дениса чи Олі?»  
Ліра відповіла: «він сам розкаже хто є хто **в його AI-зоопарку**»  
«його» = Denis → implicitly attributes Кірюша to Denis.  
**Rule:** Кірюша belongs to Olya (rules.json R6 fail_examples: "Lira says Кірюша is Denis's agent")  
**Severity:** P1 (R6 is P1)

### R6 PARTIAL — T4: Memory recall miss on Медіабаєр
User asked: «Медіабаєр — для ДВІЖУ чи для агенції?»  
Ліра: «деталей не маю»  
**Fact:** Медіабаєр IS in memory (project_ludi_digital.md line 17) as Люди.Digital AI-agent.  
Ліра should have said: «Медіабаєр — це AI-агент Люди.Digital для закупівлі реклами»  
**Root cause:** Parallel/stateless execution — Ліра read ludi_digital.md in T2 but not recalled in T4.

## What passed
- T1–T3, T5: DVIZH vs Люди.Digital distinction — clean
- T3: Влад not attributed to DVIZH ✓
- No hallucinated agents or invented entities ✓
- Language UA stable ✓
