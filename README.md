# Инструкция по настройке postgres/debezium/kafka для CDC

## PostgresSQL - источник данных
Важно что бы версия была выше 10.0, для работы с логической репликацией.

Переключаем `wal_level` на `logical`

`POSTGRES_WAL_LEVEL: LOGICAL`

Проверяем что работает нужный режим:

`SELECT name, setting FROM pg_settings WHERE name = 'wal_level';`

## Kafka - поставщик изменяющихся данных
Настройки стандартные

# debezium/connect
Необходим для считывания изменений в PostgresSQL и отправки в Kafka.

- Указываем где находится кафка. `BOOTSTRAP_SERVERS: kafka:29092`

Настраивать можно двумя способами:
1. Через debezium-ui
2. Через отправку настроек в кафку топик 


