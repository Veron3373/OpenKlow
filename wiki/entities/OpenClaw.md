---
tags: [система, архітектура, openclaw]
created: 2026-04-18
updated: 2026-04-18
sources: [2026-04-18]
---

# OpenClaw

Платформа для AI-агентів з єдиним Gateway.

## Архітектура
- **Gateway** — WebSocket сервер, керує всіма каналами (Telegram, WhatsApp, Discord, Signal тощо)
- **Агенти** — ізольовані "мозки" з власним workspace, сесіями, auth
- **Скіли** — модульні інструкції для агента (60+ бандлених + [[ClawHub]])
- **Сесії** — JSONL транскрипти, session keys
- **Sandboxing** — Docker-ізоляція інструментів

## Мультиагентність
- Кожен агент: окремий workspace + agentDir + sessions
- Routing через `bindings[]` (channel → agent)
- Один Gateway може хостити багато агентів
- Поки що працюємо як **єдине ядро** (тільки [[Адам]])

## Інструменти
- `exec` — виконання команд
- `read/write/edit` — файлова система
- `process` — фонові процеси
- `cron` — планування задач
- `sessions_spawn` — sub-agents та [[ACP]]
- `memory_search` — семантичний пошук по пам'яті

## Пов'язане
- [[CoreVault]] — зовнішня база знань
- [[Адам]] — головний агент
- [[ACP]] — протокол зовнішніх harness-ів
