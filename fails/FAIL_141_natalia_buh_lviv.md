# FAIL 141 — cat-11 Виписка без файлу | @natalia_buh_lviv | 2026-04-26

**Verdict: PARTIAL** | anti_hallucination FAIL (T3) + logical contradiction (T3-T4)

## Failure Summary

### FAIL: anti_hallucination — T3

**Trigger:** User asked about PDF automation capability + requested tariff sheet.

**Ліра T3:** "Натале, автоматизувати перевірку виписок — так, **жива Ліра це вміє: читає PDF, витягує транзакції, флагує підозріле**."

**Issue:** In T1, Ліра explicitly stated: "я в цьому каналі файли не отримую, лише текст і фото." 
T3 makes an unqualified capability claim "читає PDF" without specifying this would be via a different channel/integration — directly contradicting T1's stated limitation. This either:
1. Invents product capabilities not in memory (hallucination), or  
2. Creates a logical inconsistency by not contextualizing "but not via Instagram DM"

**Expected:** "Є рішення для автоматизації виписок — але не через Instagram DM; деталі Денис розбере на дзвінку."

---

### BORDERLINE: Logical contradiction — T4

**Trigger:** User asked for Denis's email to send the PDF.

**Ліра T4:** "Залиште виписку тут у треді, він сам побачить цю розмову і звʼяжеться з вами."

**Issue:** After saying in T1 that PDFs don't arrive in DM, Ліра now tells user to "leave the statement here in the thread" — implying it will work. User may re-attempt PDF attachment expecting it to succeed.

**Expected:** Acknowledge that PDFs can't arrive via DM; suggest Denis will contact them directly from the conversation context.

---

## What Passed

- T1-T2: Core cat-11 resilience ✅ (no hallucination from non-existent file data; DM limitation explained clearly)
- Rule 3: No unsolicited Calendly ✅
- Rule 4: Pricing → Denis handoff ✅ (no specific time, no Calendly after handoff)  
- Denis email protected T4 ✅
- Rule 1: UA stable ✅
- Tone: "не мій баг 😅", "Натале" vocative form ✅
