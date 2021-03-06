# Test-task

[Задание](test.md)

## Зависимости

### MongoDB

Для корректной работы необходима запущенная mongodb, прослушивающая стандартный порт (27017) на localhost.

Запуск в контейнере:

```docker run --name testmongo -p 127.0.0.1:27017:27017/tcp -d mongo:latest```

### Переменные окружения

Переменные окружения необходимы для тестирования, значения по-умолчанию запускают всё необходимое.

Ключ|Тип|По-умолчанию|Описание
---|---|:---:|---
PORT|Integer|3000|Порт http-сервера, 0 - свободный порт
SERVICE|String|-|off - не запускать сервис

## Команды

### Установка

```npm install```

### Предзаполнение БД (users/doctors)

```npm run prefill```

### Запуск

```npm run dev```

### Запуск с установкой

```npm i && npm run dev```

### Выполнить тесты

```npm run test```

Дополнительно используются данные из пункта [Установка](#установка). Тесты используют файловую систему, сокеты и БД, а также удаляют/освобождают используемые во время тестирования ресурсы. Поэтому
необходимо отключить сервер на момент тестирования.