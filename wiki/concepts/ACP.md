---
tags: [концепція, протокол, openclaw]
created: 2026-04-18
updated: 2026-04-18
sources: [OpenClaw Guide sileade]
---

# ACP (Agent Client Protocol)

Протокол для запуску зовнішніх coding harness-ів через [[OpenClaw]].

## Підтримувані harness-и
- **Codex** (OpenAI)
- **Claude Code** (Anthropic)
- **Gemini CLI** (Google)
- **Cursor**
- **OpenCode**

## Коли використовувати
- Потрібен зовнішній runtime (не нативний OpenClaw)
- Кодинг-сесії з прив'язкою до чату/треду
- Persistent harness sessions

## Коли НЕ використовувати
- Для загального керування ПК → краще окремий [[OpenClaw]] агент
- Для простих задач → нативні sub-agents

## Пов'язане
- [[OpenClaw]] — платформа
- [[Адам]] — координатор
