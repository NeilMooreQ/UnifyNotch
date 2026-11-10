# Unify Notch

Чёлка для Windows в духе Dynamic Island: компактная полоска у верхнего края экрана, которая раскрывается при наведении и собирает в одном месте музыку, таймеры, файлы, уведомления и устройства. Вместе с ней — окно Unify с настройками устройств, тренажёрами, менеджером паролей и обновлениями драйверов.

Здесь публикуются готовые сборки. Исходный код в этом репозитории не хранится.

## Скачать

Последняя версия — в [Releases](https://github.com/NeilMooreQ/UnifyNotch/releases/latest): файл `UnifyNotch.exe`, установка не нужна.

Файл не подписан сертификатом, поэтому при первом запуске Windows может показать окно SmartScreen с «Неизвестный издатель». Чтобы запустить: «Подробнее» → «Выполнить в любом случае».

**Требования:** Windows 11 x64 (на Windows 10 не проверялось), видеокарта с поддержкой Direct3D 12.

## Возможности

**Чёлка**
- Раскрывается при наведении, не забирая фокус у текущего приложения; прячется над полноэкранными приложениями, оставляя язычок.
- Музыка (Windows SMTC), таймеры, будильники, секундомер, фокус, мировое время.
- Файлы: полка для перетаскивания, последние загрузки, снимки экрана и записи.
- Уведомления о загрузках, заряде, сети, микрофоне и событиях, с историей.
- Пункт управления: Wi-Fi, Bluetooth, яркость, «Не беспокоить», звук и микшер.
- Радиальное меню по удержанию клавиши, захват экрана, QR-сканер, пипетка.

**Окно Unify**
- Устройства: клавиатуры VIA, мыши Logitech HID++, микрофоны HyperX QuadCast, графические планшеты, геймпады, кодеки Bluetooth-наушников; заряд устройств.
- Тренажёры мыши, клавиатуры и геймпада с историей.
- Пароли: несколько баз KDBX, генератор, одноразовые коды, автонабор, SSH-агент.
- Квоты ИИ: Codex, Claude Code и ZCode по уже выполненному входу в их CLI.
- Обновления драйверов NVIDIA, AMD и Alternative A2DP с официальных сайтов, CLI Codex и Claude Code.
- «Система»: нагрузка и железо компьютера. Подсветка через OpenRGB SDK.

## Обновления

Unify Notch проверяет этот репозиторий, когда открыта страница «Обновления» (не чаще раза в 10 минут) или по кнопке «Проверить сейчас». Новая версия скачивается и ставится только по нажатию: файл сверяется по размеру и SHA-256 из GitHub, старая версия сохраняется рядом и возвращается, если новая не запустится.

## Данные и удаление

Настройки и данные хранятся в `%LOCALAPPDATA%\UnifyNotch`.

Чтобы удалить:
1. В «Основные» выключи «Запускать вместе с Windows».
2. Выйди из Unify: «Выйти из Unify» в «Основные» или в меню значка в трее.
3. Удали `UnifyNotch.exe` и папку `%LOCALAPPDATA%\UnifyNotch`.

## Сеть и приватность

Unify Notch не собирает телеметрию и ничего не отправляет разработчику. Запросы в сеть идут только для функций, которые ими пользуются:

| Функция | Куда | Когда и как выключить |
|---|---|---|
| Драйверы | `www.nvidia.com`, `gfwsl.geforce.com` (запрос содержит модель видеокарты), `www.amd.com`, `drivers.amd.com`, `www.intel.com`, `www.bluetoothgoodies.com` | Раз в 6 часов; «Обновления» → «Проверять обновления» или модуль «Драйверы видеокарты». Установщики скачиваются только по нажатию. |
| Обновления Unify Notch | `api.github.com`, `github.com` (этот репозиторий) | При открытии «Обновления» и по кнопке. |
| Версии Codex и Claude Code | `registry.npmjs.org` | При открытии «Обновления»; модуль «Квоты ИИ». |
| Квоты ИИ | `api.anthropic.com` (со входом Claude Code), локальный `codex app-server`, `api.z.ai` и `zcode.z.ai` (со входом ZCode) | Только с включённым модулем «Квоты ИИ». Токены берутся из входа в CLI и не сохраняются в базе Unify. |
| Проверка паролей на утечки | `api.pwnedpasswords.com` получает первые 5 символов SHA-1 хеша пароля, сам пароль не покидает компьютер | Выключена, пока её не включить в «Пароли» (модуль «Пароли KeePass»). |

Подсветка через OpenRGB подключается только к серверу OpenRGB SDK на этом компьютере.

## Сторонние компоненты

[![Made with Slint](https://raw.githubusercontent.com/slint-ui/slint/master/logo/MadeWithSlint-logo-whitebg.png)](https://slint.dev)

Интерфейс сделан на [Slint](https://slint.dev) (Slint Royalty-free Desktop, Mobile, and Web Applications License 2.0). Также используются:

| Компонент | Лицензия |
|---|---|
| [Skia](https://skia.org) через [skia-safe](https://github.com/rust-skia/rust-skia), [wgpu](https://github.com/gfx-rs/wgpu), [winit](https://github.com/rust-windowing/winit) | BSD-3-Clause; MIT или Apache-2.0 |
| [Open-G-Hub](https://github.com/Sharper-Flow/Open-G-Hub) (кодек HID++) | MIT |
| [OpenTabletDriver](https://github.com/OpenTabletDriver/OpenTabletDriver) (описания моделей планшетов) | LGPL-3.0 |
| [keepass-rs](https://github.com/sseemayer/keepass-rs), [rqrr](https://github.com/WanzenBug/rqrr), [ssh-key](https://github.com/RustCrypto/SSH), [regex](https://github.com/rust-lang/regex), [rusqlite](https://github.com/rusqlite/rusqlite) (SQLite — public domain) | MIT или Apache-2.0 |
| Публикация QuietHours (Rafael Rivera) — идентификаторы интерфейсов «Не беспокоить» | MIT |
| Анимированные эмодзи из коллекции Telegram | правообладатель — Telegram |
