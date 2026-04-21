# agent-lira-tester

Trinity-compatible QA-агент для автоматичного тестування `lira-ig-v2`.

## Що робить

Кожні 10 хвилин:
1. Бере наступного персонажа з `personas.json`
2. Симулює повний діалог з Лірою (через `mcp__trinity__chat_with_agent`)
3. Оцінює діалог проти `rules.json` (PASS/FAIL per rule)
4. Зберігає транскрипт у `dialogs/`, FAIL-и у `fails/`
5. Оновлює `REPORT.md`
6. `git commit + push`

Після 50 — генерує нові edge cases (Mode B).

## Структура

- `CLAUDE.md` — процедура агента
- `personas.json` — 50 скриптованих персонажів
- `rules.json` — правила Ліри + pass/fail критерії
- `state/next.txt` — курсор у черзі
- `dialogs/` — транскрипти
- `fails/` — FAIL-и окремо
- `generated_personas/` — Mode B output
- `REPORT.md` — live звіт
- `docs/` — контекст (fixes, handoff)

## Запуск

Через Trinity:
```
mcp__trinity__create_agent(
  name="lira-tester",
  template="github:volosovd-fun/agent-lira-tester"
)
```

Потім створити schedule `*/10 * * * *` з message "Run next persona test".

## Стан

🚧 V0.1 — базова процедура, 50 персонажів, режим B на черзі.
