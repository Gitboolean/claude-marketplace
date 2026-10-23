---
name: hello
description: >
  Starter skill of the my-toolkit plugin. Use when the user says "hello toolkit",
  "перевір my-toolkit" or asks whether my-toolkit is installed. Replace this skill
  with a real one.
---

# Hello

Заготовка, щоб перевірити, що плагін `my-toolkit` встановлений і скіли підхоплюються.

## Workflow

1. Скажи, що плагін `my-toolkit` працює, і назви його версію з `${CLAUDE_PLUGIN_ROOT}/.claude-plugin/plugin.json`.
2. Підкажи, як додати новий скіл: створити `skills/<name>/SKILL.md` у `plugins/my-toolkit/`, підняти `version` і запушити.
