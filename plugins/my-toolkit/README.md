# my-toolkit

Мій особистий плагін для Claude Code, зібраний на основі [sdlc](https://github.com/genkovich/sdlc) і перероблений під себе. Описи скілів, агентів і шаблони документів — українською.

## Що всередині

**Скіли**

- `interview` — ідеація нової фічі або продукту: інтерв'ю, дослідження конкурентів, три стратегічні підходи, погляд трьох ролей, devil's advocate, RICE і здійсненність. Результат — `docs/features/<slug>/idea-brief.md` (або `docs/idea-brief.md` у порожній теці).
- `fix-term` — фіксує доменні терміни в `CONTEXT.md`: одне канонічне визначення і з чим термін плутають.

**Агенти** (їх викликає `interview`)

| Агент | Фаза | Що робить |
|---|---|---|
| `researcher` | 4 | шукає конкурентів і суміжні рішення |
| `strategist` | 5 | пропонує три різні підходи |
| `analyst` | 6 | оцінює підходи очима інженера, бізнесу і UX |
| `devils-advocate` | 8 | шукає, як ідея може провалитися |

Наступні етапи (`write-prd`, `scaffold`, `architecture-design`) поки беруться з плагіна `sdlc`, тож його варто тримати встановленим.

## Встановлення

```
/plugin marketplace add Gitboolean/claude-marketplace
/plugin install my-toolkit@gitboolean
```

Запуск: `/my-toolkit:interview <slug>` або просто «зафіксуй ідею …».

## Як додати компонент

- скіл: `skills/<name>/SKILL.md`
- команда: `commands/<name>.md`
- агент: `agents/<name>.md`

Після змін підніми `version` у `.claude-plugin/plugin.json` і в `.claude-plugin/marketplace.json`.
