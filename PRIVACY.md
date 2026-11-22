# Политика конфиденциальности Unify Notch

*English version below.*

Обновлено: 22 ноября 2026 г.

Unify Notch — приложение для Windows, которое работает на вашем компьютере. У Unify нет учётных записей, рекламы и аналитики. Разработчик не собирает и не получает ваши данные, кроме случаев, когда вы сами отправляете их через функции, описанные ниже.

## Что хранится на компьютере

Настройки, история, пути к базам паролей и другие данные приложения хранятся в папке `%LOCALAPPDATA%\UnifyNotch` на вашем компьютере. Базы паролей — это зашифрованные файлы KDBX. Мастер-пароль никуда не сохраняется, если вы сами не включили «Открывать при входе в Windows»: тогда он защищён средствами Windows (DPAPI) для вашей учётной записи.

## Когда Unify обращается к сети

Только когда вы пользуетесь соответствующей функцией:

- **Обновления** — проверка и загрузка новой версии с GitHub (`github.com`).
- **Драйверы** — проверка и загрузка с официальных сайтов производителей (NVIDIA, AMD, Intel и других).
- **Версии Codex и Claude Code** — запрос к `registry.npmjs.org`.
- **Квоты ИИ** — запросы к Anthropic и Z.ai с вашим уже выполненным входом в их CLI, только с включённым модулем «Квоты ИИ». Токены не сохраняются в Unify.
- **Пароли**: значки сайтов загружаются с самих сайтов; проверка утечек через Have I Been Pwned отправляет только первые 5 символов хеша SHA-1 пароля и только после вашего согласия.
- **Питомцы (игра)** — подключение к серверу Unify с вашим ником и состоянием питомца.
- **«Отправить сведения об устройствах»** — отправка технических данных об устройствах на сервер Unify только после того, как вы их просмотрели и нажали «Отправить». Имён пользователя и компьютера, серийных номеров и адресов Bluetooth в них нет.

## Синхронизация баз паролей с облаками

Базу паролей можно хранить на своём сервере (WebDAV, SFTP) или в Google Drive, Microsoft OneDrive и Dropbox. Если вы подключаете облако:

- Вход выполняется на странице сервиса в вашем браузере. Unify не видит ваш пароль от облака.
- Unify использует доступ только для того, чтобы показать вам папки и файлы `.kdbx`, скачать выбранную вами базу и выгрузить её после ваших изменений.
- База шифруется на вашем компьютере ещё до выгрузки; облако получает только зашифрованный файл.
- Токен доступа хранится только на вашем компьютере, защищённый Windows (DPAPI). Пароли серверов WebDAV и SFTP хранятся так же.
- Данные из облаков не передаются разработчику и третьим лицам, не используются для рекламы и обучения моделей ИИ.
- Если удалить базу из списка в Unify, сохранённый токен удаляется. Доступ можно отозвать и на стороне сервиса: [Google](https://myaccount.google.com/permissions), [Microsoft](https://account.live.com/consent/Manage), [Dropbox](https://www.dropbox.com/account/connected_apps).

Использование данных, полученных через API Google, соответствует [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), включая требования Limited Use.

## Расширение для браузера «Unify Пароли»

Расширение для Chrome, Edge, Firefox и других браузеров подставляет логины, пароли и коды 2FA из Unify Notch на вашем компьютере.

- Расширение общается только с программой Unify Notch на этом же компьютере (native messaging). Своих серверов у расширения нет; оно ничего не отправляет разработчику или третьим лицам и не содержит аналитики и рекламы.
- Чтобы найти записи сайта, расширение передаёт Unify адрес открытой страницы. Логины и пароли расширение получает от Unify только для подстановки в выбранную вами форму и нигде их не хранит.
- После входа или регистрации на сайте расширение передаёт Unify введённые логин и пароль, чтобы спросить «Сохранить пароль?». Без вашего «Сохранить» они не записываются и через 10 минут забываются.
- Расширение хранит в браузере только служебные данные: ключ подключения к Unify, последнюю использованную запись для сайта (её идентификатор, не пароль) и на несколько минут — запись, выбранную на первом шаге входа.
- Расширение может выключить встроенное сохранение паролей браузера; это можно вернуть флажком в окне расширения.

## Связь

Вопросы и запросы — через [Issues этого репозитория](https://github.com/NeilMooreQ/UnifyNotch/issues).

---

# Unify Notch Privacy Policy

Updated: November 22, 2026

Unify Notch is a Windows application that runs on your computer. It has no user accounts, no ads and no analytics. The developer does not collect or receive your data, except when you send it yourself through the features described below.

## What is stored on your computer

Settings, history, paths to password databases and other app data are stored in `%LOCALAPPDATA%\UnifyNotch` on your computer. Password databases are encrypted KDBX files. A master password is never stored unless you turn on "Open at Windows sign-in"; it is then protected by Windows (DPAPI) for your account.

## When Unify uses the network

Only when you use the related feature:

- **Updates** — checking for and downloading new versions from GitHub (`github.com`).
- **Drivers** — checks and downloads from the vendors' official sites (NVIDIA, AMD, Intel and others).
- **Codex and Claude Code versions** — a request to `registry.npmjs.org`.
- **AI quotas** — requests to Anthropic and Z.ai with your existing sign-in to their CLIs, only with the "AI quotas" module on. The tokens are not stored by Unify.
- **Passwords**: site icons are fetched from the sites themselves; the Have I Been Pwned breach check sends only the first 5 characters of the password's SHA-1 hash, and only after you agree.
- **Pets (game)** — a connection to the Unify server with your nickname and your pet's state.
- **"Send device details"** — technical details about your devices go to the Unify server only after you have reviewed them and pressed Send. They contain no user or computer names, serial numbers or Bluetooth addresses.

## Syncing password databases with cloud storage

A password database can be kept on your own server (WebDAV, SFTP) or in Google Drive, Microsoft OneDrive and Dropbox. When you connect a cloud service:

- You sign in on the provider's page in your browser. Unify never sees your cloud password.
- Unify uses its access only to show you folders and `.kdbx` files, to download the database you choose and to upload it after your changes.
- The database is encrypted on your computer before it is uploaded; the cloud only receives the encrypted file.
- The access token is stored only on your computer, protected by Windows (DPAPI). WebDAV and SFTP server passwords are stored the same way.
- Data from cloud services is not shared with the developer or any third party, and is not used for advertising or for training AI models.
- Removing the database from Unify's list deletes its stored token. You can also revoke access with the provider: [Google](https://myaccount.google.com/permissions), [Microsoft](https://account.live.com/consent/Manage), [Dropbox](https://www.dropbox.com/account/connected_apps).

Unify Notch's use and transfer of information received from Google APIs adheres to the [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy), including the Limited Use requirements.

## The "Unify Passwords" browser extension

The extension for Chrome, Edge, Firefox and other browsers fills in sign-ins, passwords and 2FA codes from Unify Notch on your computer.

- The extension talks only to the Unify Notch app on the same computer (native messaging). It has no servers of its own; it sends nothing to the developer or any third party and has no analytics or ads.
- To find a site's entries, the extension gives Unify the address of the open page. It receives sign-ins and passwords from Unify only to fill the form you chose and stores them nowhere.
- After you sign in or sign up on a site, the extension gives Unify the sign-in and password you entered, to ask "Save password?". Nothing is saved without your "Save", and the offer is forgotten after 10 minutes.
- The extension keeps only service data in the browser: the key that pairs it with Unify, the entry last used on a site (its identifier, not the password) and, for a few minutes, the entry chosen on the first step of a sign-in.
- The extension may turn off the browser's own password saving; a checkbox in the extension's window turns it back on.

## Contact

Questions and requests: [this repository's Issues](https://github.com/NeilMooreQ/UnifyNotch/issues).
