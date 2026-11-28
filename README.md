# 🎬 VK Видео — Плагин для Lampa

[![Lampa Plugin](https://img.shields.io/badge/Lampa-Plugin-blue?style=flat-square)](https://github.com/Sophiedevops/lampa-vkvideo-plugin)
[![VK Video API](https://img.shields.io/badge/VK%20Video-API%205.236-0077FF?style=flat-square)](https://vkvideo.ru)
[![Platform](https://img.shields.io/badge/Platform-Smart%20TV%20%7C%20Android%20TV%20%7C%20Web-success?style=flat-square)](#)
[![Languages](https://img.shields.io/badge/Languages-ru%20%7C%20uk%20%7C%20en%20%7C%20be-orange?style=flat-square)](#)

Неофициальный плагин **VK Видео** для медиацентра [Lampa](https://github.com/yumata/lampa).
Каталог, поиск, прямые трансляции и VOD прямо в вашем интерфейсе — без лишних переходов.

---

### 🔐 Нативный транспорт и безопасность

- 🛡️ **Android TV / Android Lampa:** все запросы к API идут через нативный HTTP-транспорт (`Lampa.Reguest().native()` + `JSON.parse()`) **без fallback на JSONP** — это исключает выполнение произвольного JS (RCE) из ответов API. *(В Desktop Web из-за ограничений CORS браузера используется JSONP.)*
- 🔒 **Защита от XSS и CSS-инъекций:** экранирование пользовательских данных (`esc()`), строгая валидация ссылок (`safeHttpUrl()`).
- ✅ **Белый список `iframe` и `postMessage`:** встраивание плеера разрешено только с доверенных доменов `https://vkvideo.ru` и `https://vk.com` с проверкой `event.origin`.

---

### ✨ Возможности

- ♾️ **Бесконечный динамический скролл** во всех разделах и поиске с дедупликацией карточек (без повторов) и отображением прогресса страниц.
- 🔍 **Глобальный поиск Lampa:** полная совместимость с контрактом `Lampa.Search.addSource` (`params`, отмена устаревших запросов `onCancel`, `onMore`, `onBack`).
- 🎚️ **Прямые потоки VOD (`144p–4K / MP4`)** и **прямые эфиры / Live-трансляции (`HLS / NativeHLS`)** + выбор качества прямо в плеере.
- ⏱️ **Точные таймкоды продолжения просмотра**, бейджи `%` на карточках, 20-минутный кэш потоков и защита от повторного запуска плеера.
- 🌍 **Локализация:** 4 языка интерфейса (`ru`, `uk`, `en`, `be`).

---

### 🎥 Поддерживаемые плееры

- 📱 **Внешний Android-плеер (Vimu и др.)** — аппаратный нативный HLS / MP4 (включая запуск из «Истории просмотра»).
- 📺 **Встроенный плеер Lampa** — автоматический приоритет прямого `MP4` без CORS-ошибок + `NativeHLS` для Live-трансляций.
- 🌐 **Плеер VK (Desktop Web)** — встроенный плеер VK с описанием, лайками и комментариями.

---

### 📲 Установка в Lampa (Ссылки для подключения)

* **Вариант 1 (Githack CDN — лучший для обхода блокировок ТВ):**
  `https://raw.githack.com/Sophiedevops/lampa-vkvideo-plugin/main/vkvideo.js`

* **Вариант 2 (Statically CDN — резервный прокси):**
  `https://cdn.statically.io/gh/Sophiedevops/lampa-vkvideo-plugin@main/vkvideo.js`

* **Вариант 3 (Прямая ссылка GitHub):**
  `https://raw.githubusercontent.com/Sophiedevops/lampa-vkvideo-plugin/main/vkvideo.js`

---

### 🚀 Быстрый старт

1. Откройте в Lampa: **Настройки ⚙️ → Расширения**
2. Нажмите **Добавить плагин**
3. Вставьте выбранную ссылку и перезапустите Lampa — в боковом меню появится раздел **VK Видео**.
