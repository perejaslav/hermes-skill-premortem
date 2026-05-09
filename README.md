# Premortem Skill for Hermes Agent

> Адаптация методологии премортема (Канеман, Кляйн) для Hermes Agent.
> Past-tense failure narrative — находит дыры в плане с 6 углов за 10–15 минут.

Оригинальный скилл для Claude Code: [AndyShaman/premortem](https://github.com/AndyShaman/premortem)

## Установка

```bash
hermes skill install https://github.com/perejaslav/hermes-skill-premortem
```

## Использование

Скажи в любой момент:

- «давай премортем плана X»
- «найди дыры в этом плане»
- «проверь план на прочность»

## Структура

```
premortem/
├── SKILL.md                       # ядро: 4 фазы
└── references/
    ├── angle-pool.md              # типы планов → 6 углов зрения
    ├── bias-checklist.md          # 6 биасов Канемана
    ├── frame-language.md          # речевые приёмы
    ├── helper-prompt-template.md  # промпт для субагентов
    └── methodology.md             # научное обоснование
```

## Что делает

1. **Pre-flight** — собирает контекст плана (предмет, аудитория, успех, горизонт)
2. **Silent scan** — 3 параллельных субагента находят 5–8 дыр с разных углов
3. **Live dialog** — по каждой дыре варианты решений, пользователь выбирает
4. **Persist** — сохраняет результат в `/root/outputs/premortem/<slug>.md`

Встроены: bias check (6 биасов), reverse premortem, rerun logic.

## Лицензия

MIT
