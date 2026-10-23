# my-toolkit

Мій особистий плагін для Claude Code, зібраний на основі [sdlc](https://github.com/genkovich/sdlc) і перероблений під себе. Усе — описи, інструкції, шаблони документів — українською.

## Що всередині

**Скіли**

- `interview` — ідеація нової фічі або продукту: інтерв'ю, дослідження конкурентів, три стратегічні підходи, погляд трьох ролей, devil's advocate, RICE і здійсненність. Результат — `docs/features/<slug>/idea-brief.md` (або `docs/idea-brief.md` у порожній теці).
- `write-prd` — з брифу і глосарію робить перевірений `docs/features/<slug>/PRD.md`: user stories, критерії приймання в бізнес-формі, NFR, KPI, сократівська перевірка кожного елемента і критик у чистому контексті.
- `clarify-prd` — прочісує готовий PRD на 8 класів неоднозначностей (власний прохід + `devils-advocate` у чистому контексті) і закриває кожну: уточнює PRD на місці або відкладає в §8 з відповідальним і терміном.
- `fix-term` — фіксує доменні терміни в `CONTEXT.md`: одне канонічне визначення і з чим термін плутають.

**Агенти**

| Агент | Хто запускає | Що робить |
|---|---|---|
| `researcher` | `interview`, фаза 4 | шукає конкурентів і суміжні рішення |
| `strategist` | `interview`, фаза 5 | пропонує три різні підходи |
| `analyst` | `interview`, фаза 6 | оцінює підходи очима інженера, бізнесу і UX |
| `devils-advocate` | `interview`, фаза 8; `clarify-prd`, крок 3 | шукає, як ідея може провалитися / де PRD неоднозначний |
| `critic` | `write-prd`, крок 8 | шукає розходження між секціями PRD після правок |

## Шлях

```
/my-toolkit:interview <slug>   →  idea-brief.md
/my-toolkit:fix-term <slug>    →  CONTEXT.md (якщо ще немає)
/my-toolkit:write-prd <slug>   →  PRD.md + .size
/my-toolkit:clarify-prd <slug> →  PRD.md без неоднозначностей
/sdlc-architecture-design <slug> → далі — етапи плагіна sdlc
```

Наступні етапи (`architecture-design`, `scaffold` і далі) поки беруться з плагіна `sdlc`, тож його варто тримати встановленим.

## Налаштування

`write-prd` при першому запуску створює `.claude/my-toolkit.local.md` (глибина інтерв'ю за замовчуванням для `write-prd` і `clarify-prd`) і додає `.claude/*.local.md` у `.gitignore`. Опис ключів — `skills/_shared/settings.md`.

## Встановлення

```
/plugin marketplace add Gitboolean/claude-marketplace
/plugin install my-toolkit@gitboolean
```

## Як додати компонент

- скіл: `skills/<name>/SKILL.md`
- команда: `commands/<name>.md`
- агент: `agents/<name>.md`

Після змін підніми `version` у `.claude-plugin/plugin.json` і в `.claude-plugin/marketplace.json`.
