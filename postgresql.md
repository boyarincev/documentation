# PostgreSQL

[Документация по PostgreSQL](https://www.postgresql.org/docs/9.6/static/index.html)

### Psql

Консольная утилита для доступа к базе \(sql запросы\).

[Инструкция по работе с psql](https://postgrespro.ru/docs/postgrespro/9.6/app-psql)

[Кириллица в psql](http://www.iu5bmstu.ru/index.php/PostgreSQL_-_Кириллица_в_psql_под_Windows)

### Управление сервером \(рестарт, старт, шутдаун\)

[Утилита для управления сервером PostgreSQL - pg-ctl](https://www.postgresql.org/docs/9.3/static/app-pg-ctl.html) \(рестарт, старт, шутдаун\)

```
pg_ctl -D . restart
```

. - это путь до инстанса сервера, который перезагружается

Обычно путь до инстанса - "C:\Program Files\PostgreSQL\data\pg95"

### Доступ к метаданным

Посмотреть какие сейчас блокировки в базе - [view pg\_locks](https://www.postgresql.org/docs/9.6/static/view-pg-locks.html)

[Другие системные вью и таблицы постгреса](https://www.postgresql.org/docs/9.6/static/catalogs.html) \(доступ ко всем метаданным\)

### Cборщики статистики

#### Посмотреть текущие соединения с БД

```SQL
SELECT * FROM pg_stat_activity;
```

[Остальные сборщики статистики PostgreSQL](https://www.postgresql.org/docs/9.6/static/monitoring-stats.html) \(pg stat activity выше пример одного из таких сборщиков\)

[Системные функции](https://www.postgresql.org/docs/current/static/functions-info.html) дающие доступ к текущей сессии \(current\_database, current\_query и т.д.\)

### Concurrency Control

[Concurrency Control](https://www.postgresql.org/docs/9.6/static/mvcc.html) в PostgreSQL - раздел официальной документации про транзакции и блокировки.

### Путь до БД сервера

```
C:\Program Files\PostgreSQL\data\pg95
```

### Путь до места хранения логов

```
C:\Program Files\PostgreSQL\data\logs\pg95
```

Похоже что pg95 - это название инстанса сервера.

### Просмотр настроек - show sql команда

```
show config_file --местоположение текущего конфиг файла
show all --показать все текущие настройки постгреса
```

```
SELECT pg_terminate_backend(pg_stat_activity.pid)
 FROM pg_stat_activity
 WHERE pg_stat_activity.datname = 'DataCollect-Concurrent-Stress-Test-4'
   AND pid <> pg_backend_pid();
```

### Убить все коннекты к базе

You can use [pg\_terminate\_backend\(\)](http://www.postgresql.org/docs/current/static/functions-admin.html) to kill a connection. You have to be superuser to use this function. This works on all operating systems the same.

```
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

```
REVOKE CONNECT ON DATABASE dbname FROM PUBLIC, username; --это навсегда?
```

[оригинал](https://stackoverflow.com/questions/5108876/kill-a-postgresql-session-connection)



### Работа с sequence

```
SELECT nextval('data."dim_Perfomance_Load_Dimension_49_id"');
```

### Работа с транзакциями

Посмотреть что есть заблокированного в транзакциях есть сейчас

```
SELECT * FROM pg_locks 
```

[pg\_locks](https://www.postgresql.org/docs/9.5/static/view-pg-locks.html)

Вывести больше информации о соединении в котором эта транзакция открыта

```
SELECT * FROM pg_locks pl LEFT JOIN pg_stat_activity psa
    ON pl.pid = psa.pid;
```

колонка "relation" в результирующей таблице указывает на таблицу [pg\_class](https://www.postgresql.org/docs/9.5/static/catalog-pg-class.html) в которой можно посмотреть, что за ресурс заблокирован.

Запрос в pgclass по идентификатору из таблицы pg\_locks

```
SELECT * FROM pg_class WHERE oid = 359894
```

Пример работы с транзакцией

Начинаем транзакцию и лочим таблицу

```
BEGIN;
LOCK TABLE data."dim_Perfomance_Load_Dimension_49" IN EXCLUSIVE MODE;
```

В другом окне пытаемся вставить в нее строку

```
INSERT INTO data."dim_Perfomance_Load_Dimension_49" ("Id", "SortOrder") VALUES (4, 4)
```

Так как таблица заблокирована, соединение будет висеть

Завершаем транзакцию в первом окне

```
COMMIT;
```

Снова пытаемся заинсертить

```
INSERT INTO data."dim_Perfomance_Load_Dimension_49" ("Id", "SortOrder") VALUES (4, 4)
```





