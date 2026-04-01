# MTGTCL

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
- умеет показывать ссылки подключения, логи, менять порт/домен, обновлять secret

## Команды
```bash
mtgctl install                 Установка/настройка (спросит порт/домен/апстрим)
mtgctl status                  Статус контейнера
mtgctl start | stop | restart  Управление
mtgctl logs                    Просмотр логов
mtgctl link                    Показать tg:// и t.me ссылки 
mtgctl config                  Показать текущий config.toml и upstreams.list
mtgctl gen-secret [domain]     Сгенерировать FakeTLS secret (hex, ee...)
mtgctl rotate-secret           Ротация secret
mtgctl set-domain <domain>     Смена FakeTLS-домена
mtgctl set-port <port>         Смена порта
mtgctl update                  Обновление контейнера
mtgctl uninstall               Удаление контейнера и конфигов
```

## Требования

- Ubuntu
- root-доступ (`sudo`)
- открытый TCP-порт для клиентов MTProto

