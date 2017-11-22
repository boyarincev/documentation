# PostgreSQL

[Документация по PostgreSQL](https://www.postgresql.org/docs/9.6/static/index.html)

### Psql

[Инструкция по работе с psql](https://postgrespro.ru/docs/postgrespro/9.6/app-psql)

[Кириллица в psql](http://www.iu5bmstu.ru/index.php/PostgreSQL_-_%D0%9A%D0%B8%D1%80%D0%B8%D0%BB%D0%BB%D0%B8%D1%86%D0%B0_%D0%B2_psql_%D0%BF%D0%BE%D0%B4_Windows)

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

[Системные функции](https://www.postgresql.org/docs/current/static/functions-info.html) дающие доступ к текущей сессии \(current\_database,_ _current\_query и т.д.\)

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


