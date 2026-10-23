# my-toolkit

Мій особистий плагін для Claude Code.

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
