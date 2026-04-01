# mtgctl

Утилита для управления `mtg` (MTProto FakeTLS proxy) через Docker.


## Быстрая установка
```bash
sudo curl -fsSL https://raw.githubusercontent.com/superillegal/mtgctl/refs/heads/main/mtgctl -o /usr/local/bin/mtgctl && sudo chmod +x /usr/local/bin/mtgctl
```

Установить:
```bash
sudo mtgctl install
```


Скрипт:
- устанавливает Docker при необходимости
- скачивает образ `nineseconds/mtg:2`
- генерирует FakeTLS secret
- создаёт конфиг в `/etc/mtg`
- запускает контейнер
- умеет показывать ссылки подключения, логи, менять порт/домен, обновлять secret и настраивать SOCKS5 upstream

## Возможности

- интерактивная установка
- управление контейнером: `start`, `stop`, `restart`, `status`
- просмотр логов: `logs`
- генерация ссылок подключения: `link`
- смена порта: `set-port`
- смена FakeTLS-домена: `set-domain`
- ротация secret: `rotate-secret`
- proxy chaining через SOCKS5 upstream
- обновление контейнера: `update`
- удаление: `uninstall`

## Требования

- Ubuntu / Debian
- root-доступ (`sudo`)
- доступ в интернет
- открытый TCP-порт для клиентов MTProto

## Быстрая установка

Установить утилиту:

```bash
sudo curl -fsSL https://raw.githubusercontent.com/<YOUR_GITHUB_USERNAME>/mtgctl/main/mtgctl -o /usr/local/bin/mtgctl && sudo chmod +x /usr/local/bin/mtgctl
