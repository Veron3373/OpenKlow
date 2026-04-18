# ClaudeClaw

## Тип
source

## URL
https://github.com/earlyaidopters/claudeclaw

## Опис
Проект для запуску Claude Code CLI через Telegram бот. НЕ OpenClaw, але має корисні патерни.

## Корисні ідеї для нас
1. **Groq Whisper** — безкоштовна транскрипція голосових (whisper-large-v3)
2. **TTS cascade** — fallback між провайдерами (ElevenLabs → Gradium → local)
3. **Voice pipeline** — .oga → .ogg → Whisper → Agent → TTS → audio reply
4. **Scheduled tasks** — cron для автоматизації
5. **SQLite memory** — постійна пам'ять
6. **File sending** — маркер `[SEND_FILE:/path]` для відправки файлів
7. **Multi-agent** — паралельні спеціалізовані агенти

## Не підходить
- Заточений під Claude Code CLI, не OpenClaw
- Потребує Anthropic API або підписку Claude
- Інша архітектура сесій

## Дата вивчення
2026-04-18
