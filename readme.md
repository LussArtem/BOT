Telegram бот для invvitted, [продажа билетов, ~формирование чека~, инфа по ближайшим концертам и ссылки на новинки музыки].

В переменных окружения надо проставить API токен бота, а также адрес proxy и логин-пароль к ней.

`BOT_TOKEN` — API токен бота

`TELEGRAM_PROXY_URL` — URL прокси сервера

`TELEGRAM_PROXY_LOGIN` — логин прокси сервера

`TELEGRAM_PROXY_PASSWORD` — пароль прокси сервера

`TELEGRAM_ACCESS_ID` — ID Telegram аккаунта, от которого будут приниматься сообщения (сообщения от остальных аккаунтов игнорируются)

Использование с Docker показано ниже. Предварительно заполните ENV переменные, указанные выше, в Dockerfile, а также в команде запуска укажите локальную директорию с проектом вместо `local_project_path`. SQLite база данных будет лежать в папке проекта `db/finance.db`.

```
docker build -t tgfinance ./
docker run -d --name tg -v /local_project_path/db:/home/db tgfinance
```
