# Voice Pipeline

## Опис
Єдиний pipeline обробки голосових повідомлень для всіх агентів (Адам, Сем, Мікі).

## Архітектура
```
[Telegram Voice] → [Download .oga] → [Convert .ogg] → [Whisper STT] → [Agent Process] → [TTS] → [Send Audio]
```

## STT (Speech-to-Text)
- **Рекомендація:** Groq Whisper (безкоштовно, без картки)
- **Альтернатива:** faster-whisper (локально, офлайн)
- **Модель:** whisper-large-v3

## TTS (Text-to-Speech)
- **Провайдер:** Microsoft Edge TTS (вбудований в OpenClaw)
- **Голос:** uk-UA-OstapNeural (українська)
- **Формат:** audio-24khz-48kbitrate-mono-mp3

## Глобальна швидкість
- Зберігається в `openclaw.json` → `messages.tts.providers.microsoft.rate`
- Поточне значення: `+75%` (= 1.75x)
- Зміна в одному місці → застосовується для ВСІХ агентів
- Діапазон: від `-50%` до `+200%`

### Таблиця швидкостей
| Бажана швидкість | Значення rate |
|-----------------|---------------|
| 1.0x (нормальна) | `+0%` |
| 1.25x | `+25%` |
| 1.5x | `+50%` |
| 1.75x | `+75%` |
| 2.0x | `+100%` |
| 2.5x | `+150%` |

## Зв'язки
- [[Telegram Bot Architecture]] — загальна архітектура
- [[OpenClaw]] — платформа
