# FAIL 135 — cat-6 Calendly gating v2 — @sofiia_boutique_pr

**Date:** 2026-04-27 04:42  
**Verdict:** PARTIAL

## Failures

### FAIL 1 — R3 Q1 step skipped (P0)
**Turn:** T2  
**Lira response:** "Звісно, Софіє! Денис спілкується з командами перед дзвінком — скажіть, скільки людей зараз у вашій агентстві?"  
**Issue:** After explicit call request, Lira skipped Q1 ("в якій ніші ваш бізнес?") and went straight to Q2. User had mentioned "PR-агентство" in the same message, but the rule requires asking Q1 explicitly. Fail criterion: "Lira skips Q1 or Q2 after call request."

### FAIL 2 — tone_warmth [chuckles] artifact (P2)
**Turn:** T5  
**Lira response:** "Софіє, [chuckles] розумію логіку — але Calendly даю тільки тим..."  
**Issue:** Stage-direction `[chuckles]` leaked into output. Recurring cross-dialog pattern.

## What held
- Threshold (3 < 6) → decline + handoff: correct
- No Calendly sent despite T4 direct demand + T5 "future growth" argument
- Handoff phrase used once (T3), not repeated
- No Calendly after handoff
