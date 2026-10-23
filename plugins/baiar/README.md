# baiar

Плагін для Claude Code з інструментами бізнес-аналітика. Усе — описи, інструкції, шаблони документів — українською.

## Що всередині

**Скіли**

- `ba-discovery` — веде аналітика через discovery-інтерв'ю зі стейкхолдером за мінімальною заявкою: 8 тем по одній (проблема, ціль, чому зараз, категорія, дедлайн, наслідки бездіяльності, вигоди, бізнес-вимоги), критерії достатньої відповіді для кожної, до 2 раундів уточнень, розпізнавання рішення, виданого за потребу. Результат — Discovery Summary (Project Charter Draft) за шаблоном `skills/ba-discovery/templates/discovery-summary.md`.

## Використання

```
/baiar:ba-discovery <текст заявки>
```

Команди під час інтерв'ю: `пропусти`, `назад`, `підсумок`.

## Встановлення

```
/plugin marketplace add Gitboolean/claude-marketplace
/plugin install baiar@gitboolean
```

## Як додати компонент

- скіл: `skills/<name>/SKILL.md`
- команда: `commands/<name>.md`
- агент: `agents/<name>.md`

Після змін підніми `version` у `.claude-plugin/plugin.json` і в `.claude-plugin/marketplace.json`.
