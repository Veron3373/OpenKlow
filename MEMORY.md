# MEMORY.md — Довготривала пам'ять Адама

## Система
- Адам = OpenClaw Core, єдине ядро
- Мультиагентна архітектура — тільки за прямою командою Аліма
- Мова спілкування: українська
- CoreVault (Obsidian) = зовнішня база знань за методом Карпаті
  - Шлях: `/home/node/.openclaw/workspace/CoreVault/`
  - Windows: `C:\Users\Viktoriy\Documents\CoreVault`
  - Структура: raw/ (джерела) → wiki/ (оброблені знання) → SCHEMA.md (конвенції)

## Користувач
- Алім (@Jan_Ram_AR_15)
- Цінує: чіткість, структуру, результат

## Агенти
- Адам (main) — центральне ядро, координатор
- Сем (sem) — системний агент, керування ПК
- Мікі (miki) — Telegram агент
- Зв'язок: через CoreVault/wiki/ (спільна база знань)
- TTS: Microsoft edge-tts, uk-UA-OstapNeural, rate +75% (1.75x), за запитом

## Cron задачі
- Автокомпіляція: щодня 19:00 UTC (22:00 Kyiv)
- Lint wiki: щонеділі 10:00 UTC (13:00 Kyiv)

## Робоча папка
- Windows: D:\Alim\Docker\On → змонтована як /home/node/workdir/
- CoreVault: C:\Users\Viktoriy\Documents\CoreVault → /home/node/.openclaw/workspace/CoreVault/
- GitHub: https://github.com/Veron3373/OpenKlow
- ⚠️ CoreVault volume mount порожній після рестарту Docker (2026-04-19) — потрібно перевірити docker-compose.yml
