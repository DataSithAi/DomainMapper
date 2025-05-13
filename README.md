# DomainMapper

## Описание проекта

`DomainMapper` — инструмент на Python для разрешения доменных имен популярных сервисов в IP-адреса с последующей агрегацией маршрутов. Поддерживает работу с локальными и публичными DNS-серверами, а также предоставляет гибкие настройки через конфигурационный файл.

## 🔧 Возможности

- Разрешение доменных имен популярных сервисов в IP-адреса.

- Агрегация маршрутов в подсети /24 и /16.

- Поддержка пользовательских списков доменов и DNS-серверов.

- Гибкая настройка через config.ini.

- Возможность запуска в Docker.

## 📦 Установка

1. Клонируйте репозиторий:

```bash
git clone https://github.com/Sarmat01785/DomainMapper.git

cd DomainMapper
```

2. Установите зависимости:

```bash
pip install -r requirements.txt
```

## ⚙️ Настройка

Файл `config.ini` содержит основные параметры настройки:

- `localplatform = yes` — использовать локальный файл platformdb для списка сервисов.

- `localdns` = yes — использовать локальный файл dnsdb для списка DNS-серверов.

- `customdns = yes` — использовать пользовательский список доменов из `custom-dns-list.txt`.

Пример содержимого `platformdb`:

```bash
Google: platforms/google.txt
Facebook: platforms/facebook.txt
```

Пример содержимого `dnsdb`:

```bash 
Cloudflare: 1.1.1.1 1.0.0.1
GoogleDNS: 8.8.8.8 8.8.4.4
```

## 🚀 Использование

Запустите скрипт:

```bash
python main.py
```

Или с указанием альтернативного конфигурационного файла:

```bash
python main.py -c myconfig.ini
```

## 🐳 Запуск в Docker

Для запуска в Docker:

1. Соберите образ:

```bash
docker build -t domainmapper .
```

2. Запустите контейнер:

```bash
docker run --rm -v $(pwd):/app domainmapper
```

## 📁 Структура проекта

```bash
DomainMapper/
├── config.ini               # Конфигурационный файл
├── custom-dns-list.txt      # Пользовательский список доменов
├── dnsdb                    # Список DNS-серверов
├── main.py                  # Основной скрипт
├── platformdb               # Список сервисов и их доменов
└── requirements.txt         # Зависимости проекта
```

## 📄 Лицензия

Проект распространяется под лицензией `MIT`.


