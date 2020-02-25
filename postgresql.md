# PostgreSQL

[Документация по PostgreSQL](https://www.postgresql.org/docs/9.6/static/index.html)

## Psql

Консольная утилита для доступа к базе \(sql запросы\).

[Инструкция по работе с psql](https://postgrespro.ru/docs/postgrespro/9.6/app-psql)

[Кириллица в psql](http://www.iu5bmstu.ru/index.php/PostgreSQL_-_Кириллица_в_psql_под_Windows)

## pgcli

Более продвинутая консольная утилита для доступа к БД

[https://www.pgcli.com/](https://www.pgcli.com/)

## Управление сервером \(рестарт, старт, шутдаун\)

[Утилита для управления сервером PostgreSQL - pg-ctl](https://www.postgresql.org/docs/9.3/static/app-pg-ctl.html) \(рестарт, старт, шутдаун\)

```text
pg_ctl -D . restart
```

. - это путь до инстанса сервера, который перезагружается

Обычно путь до инстанса - "C:\Program Files\PostgreSQL\data\pg95"

Замечание: Похоже путь до инстанса нужно указывать в кавычках

## Доступ к метаданным

[Другие системные вью и таблицы постгреса](https://www.postgresql.org/docs/9.6/static/catalogs.html) \(доступ ко всем метаданным\)

## Cборщики статистики

### Посмотреть текущие соединения с БД

```sql
SELECT * FROM pg_stat_activity;
```

[Остальные сборщики статистики PostgreSQL](https://www.postgresql.org/docs/9.6/static/monitoring-stats.html) \(pg stat activity выше пример одного из таких сборщиков\)

[Системные функции](https://www.postgresql.org/docs/current/static/functions-info.html) дающие доступ к текущей сессии \(current\_database, current\_query и т.д.\)

## Путь до БД сервера

```text
C:\Program Files\PostgreSQL\data\pg95
```

## Путь до места хранения логов

```text
C:\Program Files\PostgreSQL\data\logs\pg95
```

Похоже что pg95 - это название инстанса сервера.

## Просмотр настроек - show sql команда

```text
show config_file --местоположение текущего конфиг файла
show all --показать все текущие настройки постгреса
```

```text
SELECT pg_terminate_backend(pg_stat_activity.pid)
 FROM pg_stat_activity
 WHERE pg_stat_activity.datname = 'DataCollect-Concurrent-Stress-Test-4'
   AND pid <> pg_backend_pid();
```

## Убить все коннекты к базе

You can use [pg\_terminate\_backend\(\)](http://www.postgresql.org/docs/current/static/functions-admin.html) to kill a connection. You have to be superuser to use this function. This works on all operating systems the same.

```text
SELECT
    pg_terminate_backend(pid)
FROM
    pg_stat_activity 
WHERE
-- don't kill my own connection!
    pid <> pg_backend_pid()
-- don't kill the connections to other databases
AND
    datname = 'database_name';
```

Before executing this query, you have to [REVOKE](http://www.postgresql.org/docs/current/interactive/sql-revoke.html) the CONNECT privileges to avoid new connections:

```text
REVOKE CONNECT ON DATABASE dbname FROM PUBLIC, username; --это навсегда?
```

[оригинал](https://stackoverflow.com/questions/5108876/kill-a-postgresql-session-connection)

## Работа с sequence

[Все функции в документации](https://www.postgresql.org/docs/9.1/static/functions-sequence.html)

```text
SELECT nextval('data."dim_Perfomance_Load_Dimension_49_id"');
```

## Работа с транзакциями

Посмотреть что есть заблокированного в транзакциях есть сейчас

```text
SELECT * FROM pg_locks
```

[pg\_locks](https://www.postgresql.org/docs/9.5/static/view-pg-locks.html)

Вывести больше информации о соединении в котором эта транзакция открыта

```text
SELECT * FROM pg_locks pl LEFT JOIN pg_stat_activity psa
    ON pl.pid = psa.pid;
```

колонка "relation" в результирующей таблице указывает на таблицу [pg\_class](https://www.postgresql.org/docs/9.5/static/catalog-pg-class.html) в которой можно посмотреть, что за ресурс заблокирован.

Запрос в pgclass по идентификатору из таблицы pg\_locks

```text
SELECT * FROM pg_class WHERE oid = 359894
```

Пример работы с транзакцией

Начинаем транзакцию и лочим таблицу

[LOCK](https://postgrespro.ru/docs/postgresql/9.6/sql-lock)

[Явное блокирование](https://www.postgresql.org/docs/9.5/static/explicit-locking.html)

```text
BEGIN;
LOCK TABLE data."dim_Perfomance_Load_Dimension_49" IN EXCLUSIVE MODE;
```

В другом окне пытаемся вставить в нее строку

```text
INSERT INTO data."dim_Perfomance_Load_Dimension_49" ("Id", "SortOrder") VALUES (4, 4)
```

Так как таблица заблокирована, соединение будет висеть

Завершаем транзакцию в первом окне

```text
COMMIT;
```

Снова пытаемся заинсертить

```text
INSERT INTO data."dim_Perfomance_Load_Dimension_49" ("Id", "SortOrder") VALUES (4, 4)
```

## Узнать местоположение таблицы в файловой системе

[Раздел документации о том как всё хранится в файловой системе](https://www.postgresql.org/docs/10/static/storage.html)

Определяем oid таблицы

```text
SELECT oid FROM pg_class WHERE relname = 'employees';
```

Нужно запрашивать именно колонку oid - если просто выводить все поля таблицы через звёздочку, то oid колонка не будет показываться в итоговой выборке - колонка скрытая.

```text
SELECT pg_relation_filepath(446565)
```

Покажет местоположение таблицы в файловой системе относительно местоположения БД в файловой системе \(в моём случае относительно каталога "C:\Program Files\PostgreSQL\data\pg95"\)

## Работа с oid

[Документация по oid](https://www.postgresql.org/docs/current/static/datatype-oid.html)

Там где нужно использовать oid можно сделать быстрое приведение используя имя \(имя таблицы, индекса и т.д.\)

```text
'employees'::regclass
```

Или так \(похоже нет разницы что использовать\)

```text
'employees'::regclass::oid
```

