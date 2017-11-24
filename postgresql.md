# PostgreSQL

[Документация по PostgreSQL](https://www.postgresql.org/docs/9.6/static/index.html)

### Psql

[Инструкция по работе с psql](https://postgrespro.ru/docs/postgrespro/9.6/app-psql)

[Кириллица в psql](http://www.iu5bmstu.ru/index.php/PostgreSQL_-_Кириллица_в_psql_под_Windows)

### Управление сервером \(рестарт, старт, шутдаун\)

[Утилита для управления сервером PostgreSQL - pg-ctl](https://www.postgresql.org/docs/9.3/static/app-pg-ctl.html) \(рестарт, старт, шутдаун\)

```
pg_ctl -D . restart
```

. - это путь до инстанса сервера, который перезагружается

### Доступ к метаданным

Посмотреть какие сейчас блокировки в базе - [view pg\_locks](https://www.postgresql.org/docs/9.6/static/view-pg-locks.html)

[Другие системные вью и таблицы постгреса](https://www.postgresql.org/docs/9.6/static/catalogs.html) \(доступ ко всем метаданным\)

### Cборщики статистики

#### Посмотреть текущие соединения с БД

```SQL
SELECT * FROM pg_stat_activity;
```

[Остальные сборщики статистики PostgreSQL](https://www.postgresql.org/docs/9.6/static/monitoring-stats.html) \(pg stat activity выше пример одного из таких сборщиков\)

[Системные функции](https://www.postgresql.org/docs/current/static/functions-info.html) дающие доступ к текущей сессии \(current\_database,\_ \_current\_query и т.д.\)

### Concurrency Control

[Concurrency Control](https://www.postgresql.org/docs/9.6/static/mvcc.html) в PostgreSQL

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

You can use[pg\_terminate\_backend\(\)](http://www.postgresql.org/docs/current/static/functions-admin.html)to kill a connection. You have to be superuser to use this function. This works on all operating systems the same.

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
REVOKE CONNECT ON DATABASE dbname FROM PUBLIC, username;
```

[оригинал](https://stackoverflow.com/questions/5108876/kill-a-postgresql-session-connection)

