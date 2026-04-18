# Telegram Bot Architecture

## Опис
Архітектурні патерни та можливості Telegram ботів для системи OpenClaw.

## Наші боти
| Агент | Bot Account | Роль |
|-------|------------|------|
| Адам | `default` | Центральне ядро, координатор |
| Сем | `sem` | Системний агент-керувальник ПК |
| Мікі | `miki` | (визначити роль) |

## Ключові можливості Telegram

### Commands
- `/start` — обов'язковий, початок взаємодії
- `/help` — довідка
- `/settings` — налаштування
- Command Scopes — різні команди для різних контекстів

### Inline Keyboards
- Кнопки під повідомленнями (callback buttons)
- URL buttons, switch-to-inline
- Можна редагувати без нових повідомлень

### Managed Bots
- Один бот може керувати іншим
- Корисно: Адам як головний → керує Сем/Мікі

### Bot-to-Bot Communication
- Боти можуть взаємодіяти між собою
- Через спільну базу знань або API

### Deep Linking
- `https://t.me/bot?start=param` — передача параметрів
- Для автоматизації та інтеграції

## Voice Pipeline
Рекомендований flow для голосових:
```
Голосове повідомлення
  ↓
Завантаження .oga → конвертація .ogg
  ↓
Транскрипція (Whisper)
  ↓
Обробка агентом
  ↓
TTS відповідь (edge-tts / Microsoft)
```

## TTS Налаштування (глобальне)
```json
{
  "provider": "microsoft",
  "voice": "uk-UA-OstapNeural",
  "lang": "uk-UA",
  "rate": "+75%",
  "auto": "always"
}
```
- Rate `+75%` = швидкість 1.75x
- Зміна rate в одному місці → для всіх агентів

## Whisper Транскрипція (варіанти)
| Варіант | Вартість | Примітки |
|---------|----------|----------|
| Groq Whisper | Безкоштовно | API ключ без картки, whisper-large-v3 |
| faster-whisper (локальний) | Безкоштовно | Потрібен ffmpeg + Python |
| OpenAI Whisper API | ~$0.006/хв | Найпростіше |

## Зв'язки
- [[OpenClaw]] — платформа
- [[Адам]] — головний агент
- [[Сем]] — системний агент
- [[Мікі]] — агент

## Джерела
- https://core.telegram.org/bots/features
- https://github.com/earlyaidopters/claudeclaw
- Дата: 2026-04-18
