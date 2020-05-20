# db-api.jar

## Начало работы

Приложение подготовлено к тестированию на СУБД PostgreSQL(используется образ 12.0-alpine).

### Перед установкой

1. Файл application.properties написан для использования Docker Toolbox на Windows. В случае испотзования нативного Docker Desktop под вашу ОС замените ip 192.168.99.100 на localhost.
2. Приложение запускается на 9999 порту, если нужно поменять порт запуска, то добавьте в файл application.properties строку server.port=<нужный номер порта>).

### Установка и запуск

1. Запустите в терминале команду `docker-compose up`
2. Дождитесь пока БД запустится
3. Запустите целевое приложение командой `java -jar db-api.jar`
4. Если вы сделали всё правильно, то приложение запустится и на `GET http://localhost:9999/api/cards` выдаст вам JSON с картами:
```
{
        "id": 1,
        "name": "Альфа-Карта Premium",
        "description": "Альфа-Карта вернёт ваши деньги",
        "imageUrl": "/alfa-card-premium.png"
    },
    {
        "id": 2,
        "name": "Alfa Travel Premium",
        "description": "Самая выгодная карта для путешествий",
        "imageUrl": "/alfa-card-travel.png"
    },
    {
        "id": 3,
        "name": "CashBack Premium",
        "description": "Заправь свою карту. Кэшбэк на АЗС, в кафе и ресторанах",
        "imageUrl": "/alfa-card-cashback.png"
    }
]
```
