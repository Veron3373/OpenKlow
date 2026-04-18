---
tags: [джерело, гайд, openclaw, розгортання]
created: 2026-04-18
updated: 2026-04-18
---

# OpenClaw Guide (sileade)

Повний гайд з розгортання OpenClaw з локальними моделями.

## Ключові тези

### Архітектура
- **Gateway** — WebSocket сервер (порт 18789), координує все
- **Agent (Pi Agent)** — мозок системи
- **Channels** — Telegram, WhatsApp, Slack, Discord
- **Skills** — 53 офіційні навички
- **MCP Servers** — стандартизований протокол для інструментів

### Локальні моделі (Ollama)
- Мінімум 8-12 ГБ VRAM для малих моделей (7-13B)
- 16-24 ГБ для середніх (20-40B)
- Контекст мінімум 64k токенів
- Рекомендовані: `qwen3-coder`, `glm-4.7`, `gpt-oss:20b`

### MCP-сервери
- **ComfyUI** — генерація зображень
- **Whisper** — розпізнавання мови
- **PostgreSQL** — бази даних
- **Home Assistant** — розумний дім
- **Filesystem** — безпечний доступ до файлів

### Безпека
- Docker = обов'язково
- Sandbox для виконання коду
- Composio для безпечного доступу до пошти
- Ніколи не запускати від root
- Локальні моделі вразливіші до prompt injection

### Інтеграції
- Apple Notes (`memo` CLI)
- Gmail (`gog` skill або `himalaya`)
- Apple Reminders (`remindctl`)
- Cron — вбудований планувальник

## Пов'язане
- [[OpenClaw]] — платформа
- [[Метод Карпаті]] — підхід до бази знань
