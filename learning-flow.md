Learning Flow

### Утечки памяти в Javascript

* [x] [Best practices for reducing Garbage Collector activity in Javascript](https://stackoverflow.com/questions/18364175/best-practices-for-reducing-garbage-collector-activity-in-javascript) - много советов как избежать сборку мусора
* [ ] [Javascript and Garbage collection](https://stackoverflow.com/questions/18800440/javascript-and-garbage-collection) - небольшой ответ про то как избегать сборки мусора

* [x] [**Memory Management**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management)** в Javascript - Must Read, статья с MDN**

* [x] [**Concurrency model and Event Loop in Javascript**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)** - Must Read, статья с MDN**

### Javascript

* [ ] [Iterators and generators in Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators) - MDN
* [ ] [Побитовые операции](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators)
* [ ] [Рефакторинг салона видеопроката на JavaScript](https://habrahabr.ru/post/320280/)
* [ ] Андерс Хейлсберг о нововведениях в TypeScript на конференции MS Build 2017.
  Очень интересное выступление Андерса Хейлсберга на Build 2017 о нововведениях в языке TypeScript с сильной строгой flow-sensitive системой типов \(flow typing\) - очень советую посмотреть!
  [https://channel9.msdn.com/Events/Build/2017/B8088/](https://channel9.msdn.com/Events/Build/2017/B8088/)
  Я сам практически не использую Windows в работе \(и остаюсь приверженцем Debian и Arch Linux\), но Андерс показывает классный отработанный до автоматизма экспириенс в Windows 10 и консоли, виртуозное владение TypeScript в редакторе в возможностями IDE Visual Studio Code - люблю смотреть такие выступления, это просто хай-тэк шоу и очень приятно наблюдать за работой профессионалов столь высокой квалификации!

### Angular

[Angular 1.5: Компоненты](https://habrahabr.ru/post/277087/)

### Утечки памяти в Angular

* [ ] [How does data binding work in AngularJS?](https://stackoverflow.com/questions/9682092/how-does-data-binding-work-in-angularjs) - Объяснение как биндинг работает в Angular + про время выполнения с разным количеством вотчеров и в разных браузерах
* [x] [What is the lifecycle of an AngularJS Controller?](https://stackoverflow.com/questions/16094940/what-is-the-lifecycle-of-an-angularjs-controller) - рассказывается когда уничтожается скоуп контроллера при роутинге
* [x] [Memory management in Angular applications](https://medium.com/@rlucha/memory-management-in-angular-applications-12f05499b36d) - какая-то общая вода из-за чего может утечь память
* [x] [How The $destroy Event Affects The Scope Tree In AngularJS](https://www.bennadel.com/blog/2883-how-the-destroy-event-affects-the-scope-tree-in-angularjs.htm) - про дестрой скоупа, только уже на примере ng-if
* [ ] [**Fixing Memory Leaks in AngularJS and other JavaScript Applications**](http://www.dwmkerr.com/fixing-memory-leaks-in-angularjs-applications/)** - какая-то здоровая статья, про утечки памяти в Angular !!! нужно прочитать**
* [ ] [Notes On AngularJS Scope Life-Cycle](http://onehungrymind.com/notes-on-angularjs-scope-life-cycle/) - небольшая статья про digest цикл, вотчеры и apply 

### Ограничения запросов SQL

* [ ] [SQLCommand ExecuteNonQuery Maximum CommandText Length?](https://stackoverflow.com/questions/21390537/sqlcommand-executenonquery-maximum-commandtext-length)

* [ ] [PostgreSQL - max number of parameters in “IN” clause?](https://stackoverflow.com/questions/1009706/postgresql-max-number-of-parameters-in-in-clause)

* [ ] [Is SQL IN bad for performance?](https://stackoverflow.com/questions/1013797/is-sql-in-bad-for-performance)

* [ ] [Entity Framework query slow, but same SQL in SqlQuery is fast](https://stackoverflow.com/questions/15767803/entity-framework-query-slow-but-same-sql-in-sqlquery-is-fast)

* [ ] [SQL WHERE ID IN \(id1, id2, …, idn\)](https://stackoverflow.com/questions/5803472/sql-where-id-in-id1-id2-idn)

### Ограничения размеров коллекций и массивов

* [ ] [List size limitation in C\#](https://stackoverflow.com/questions/7885294/list-size-limitation-in-c-sharp)

* [ ] [What is the Maximum Size that an Array can hold?](https://stackoverflow.com/questions/1391672/what-is-the-maximum-size-that-an-array-can-hold)

### ADO.NET

* [ ] [How do I return multiple result sets with SqlCommand?](https://stackoverflow.com/questions/12715620/how-do-i-return-multiple-result-sets-with-sqlcommand)

### Entity Framework

* [ ] [Прямой SQL в EntityFramework. Теперь со строгой типизацией](https://habrahabr.ru/post/347820/)
* [ ] [Fastest Way of Inserting in Entity Framework](https://stackoverflow.com/questions/5940225/fastest-way-of-inserting-in-entity-framework)

* [ ] [Improving bulk insert performance in Entity framework](https://stackoverflow.com/questions/6107206/improving-bulk-insert-performance-in-entity-framework)

### Deep Learning

* [ ] [Бесплатная GPU Tesla K80 для ваших экспериментов с нейросетями](https://habrahabr.ru/post/348058/)

### PostgreSQL

* [ ] [Рекурсивные запросы в PostgreSQL \(WITH RECURSIVE\)](https://habrahabr.ru/post/269497/)

* [ ] [Модуль для работы с деревом ltree](https://www.postgresql.org/docs/9.4/static/ltree.html)

* [ ] [With Queries](https://www.postgresql.org/docs/8.4/static/queries-with.html)

* [ ] [Производительность PostgreSQL](https://www.postgresql.org/docs/9.6/static/performance-tips.html) - **MR**

* [ ] [PostgreSQL Concurrency Issues](https://www.postgresql.org/files/developer/concurrency.pdf) - какая-то страння презентация 2002 года, разбираются вопросы транзакций и производительности, стоит вчитаться.

* [ ] [14.1. Using EXPLAIN](https://www.postgresql.org/docs/9.6/static/using-explain.html)

* [ ] [15.1. How Parallel Query Works](https://www.postgresql.org/docs/9.6/static/how-parallel-query-works.html)

* [ ] [Как стать спецом в Базах Данных](https://habr.com/post/429508/)

### Сsharp

* [ ] [Исследуем сопоставление с образцом в C\# 7](https://habrahabr.ru/post/347916/)
* [ ] Нюансы работы со строками: [https://msdn.microsoft.com/en-us/library/ms973919.aspx](https://msdn.microsoft.com/en-us/library/ms973919.aspx)

### Профилирование приложений

* [ ] [CodeTrack](https://getcodetrack.wordpress.com/)

### Верстка

* [ ] [Современный CSS для динозавров](https://habrahabr.ru/post/348500/)
* [ ] [**sakura**](https://github.com/oxalorg/sakura) - минималистичный css фреймворк
* [ ] [30 секунд CSS](https://habrahabr.ru/company/mailru/blog/350160/)

### Математика

* [ ] [Как читать математику](https://habrahabr.ru/post/346228/)

### Производительность БД

* [ ] [Три аспекта оптимизации \(БД и ПО\)](https://habrahabr.ru/post/349910/)

### OLAP

* [ ] Изучить Олап  [http://www.olap.ru/basic/home.asp](http://www.olap.ru/basic/home.asp)

### Строки в .NET

\[ \] [Строки в C\# и .NET](https://habr.com/post/165597/)

\[ \] [Юникод и .NET](https://habr.com/post/193048/)

\[ \] [Кодировки](http://kunststube.net/encoding/)

\[ \] [Особенности строк в .NET](https://habr.com/post/172627/)

### Как работает Javascript

* [ ] Часть 1:[Обзор движка, механизмов времени выполнения, стека вызовов](https://habrahabr.ru/company/ruvds/blog/337042/)

* [ ] Часть 2:[О внутреннем устройстве V8 и оптимизации кода](https://habrahabr.ru/company/ruvds/blog/337460/)

* [ ] Часть 3:[Управление памятью, четыре вида утечек памяти и борьба с ними](https://habrahabr.ru/company/ruvds/blog/338150/)

* [ ] Часть 4:[Цикл событий, асинхронность и пять способов улучшения кода с помощью async / await](https://habrahabr.ru/company/ruvds/blog/340508/)

* [ ] Часть 5:[WebSocket и HTTP/2+SSE. Что выбрать?](https://habrahabr.ru/company/ruvds/blog/342346/)

* [ ] Часть 6:[Особенности и сфера применения WebAssembly](https://habrahabr.ru/company/ruvds/blog/343568/)

* [ ] Часть 7:[Веб-воркеры и пять сценариев их использования](https://habrahabr.ru/company/ruvds/blog/348424/)

* [ ] Часть 8:[Сервис-воркеры](https://habrahabr.ru/company/ruvds/blog/349858/)

* [ ] Часть 9:[Веб push-уведомления](https://habrahabr.ru/company/ruvds/blog/350486/)

* [ ] Часть 10:[Отслеживание изменений в DOM с помощью MutationObserver](https://habrahabr.ru/company/ruvds/blog/351256/)

* [ ] Часть 11:[Движки рендеринга веб-страниц и советы по оптимизации их производительности](https://habrahabr.ru/company/ruvds/blog/351802/)

* [ ] Часть 12:[Сетевая подсистема браузеров, оптимизация её производительности и безопасности](https://habr.com/company/ruvds/blog/354070/)

* [ ] Часть 12:[Сетевая подсистема браузеров, оптимизация её производительности и безопасности](https://habr.com/company/ruvds/blog/354070/)

* [ ] Часть 13:[Анимация средствами CSS и JavaScript](https://habr.com/company/ruvds/blog/354438/)

* [ ] Часть 14:[Как работает JS: абстрактные синтаксические деревья, парсинг и его оптимизация](https://habr.com/company/ruvds/blog/415269/)

* [ ] Работа с абстрактными синтаксическими деревьями JavaScript - Еще одна статья про АСТ в Javascript [https://habr.com/company/jugru/blog/428628/](https://habr.com/company/jugru/blog/428628/)

* [ ] Часть 15:[Как работает JS: классы и наследование, транспиляция в Babel и TypeScript](https://habr.com/company/ruvds/blog/415377/)

* [ ] Часть 16:[Как работает JS: системы хранения данных](https://habr.com/company/ruvds/blog/415505/)

* [ ] Часть 17:[Как работает JS: технология Shadow DOM и веб-компоненты](https://habr.com/company/ruvds/blog/415881/)

* [ ] Часть 18:[Как работает JS: WebRTC и механизмы P2P-коммуникаций](https://habr.com/company/ruvds/blog/416821/)

* [ ] Часть 19:[Как работает JS: пользовательские элементы](https://habr.com/company/ruvds/blog/419831/)

### Numpy и Scipy

* [ ] Руководство [https://engineering.ucsb.edu/~shell/che210d/numpy.pdf](https://engineering.ucsb.edu/~shell/che210d/numpy.pdf)

### BigData

* [ ] Как яндекс хранит данные: [https://habr.com/company/yandex/blog/273305/](https://habr.com/company/yandex/blog/273305/)

### Чистый код

Конспект книги Роберта Мартина [https://habr.com/post/424051/](https://habr.com/post/424051/)

### Архитектура

* [ ] Хроники Архитектуры: [https://herbertograca.com/2017/07/03/the-software-architecture-chronicles/](https://herbertograca.com/2017/07/03/the-software-architecture-chronicles/)

### Идеи

Сравнить производительность двух операций:

Object -&gt; IList - с упаковкой

Object -&gt; IEnumerable&lt;object&gt; - есть упаковка?

что быстрее?

Нужно прочитать главы из книги про Перфоманс.

Как пример можно привести пример как измерять перфоманс.

Почему не создается лист интов размером инт.МаксВелью?

Get c Body

[https://stackoverflow.com/questions/978061/http-get-with-request-body](https://stackoverflow.com/questions/978061/http-get-with-request-body)

[https://stackoverflow.com/questions/17094496/what-would-a-body-in-an-http-get-look-like?noredirect=1&lq=1](https://stackoverflow.com/questions/17094496/what-would-a-body-in-an-http-get-look-like?noredirect=1&lq=1)

Entity Framework быстрый апдейт

[https://stackoverflow.com/questions/44194877/how-to-bulk-update-records-in-entity-framework](https://stackoverflow.com/questions/44194877/how-to-bulk-update-records-in-entity-framework)

PostgreSQL INSERT с RETURNING - гарантированность возвращяемого порядка.

[https://stackoverflow.com/questions/5439293/is-insert-returning-guaranteed-to-return-things-in-the-right-order](https://stackoverflow.com/questions/5439293/is-insert-returning-guaranteed-to-return-things-in-the-right-order)

[https://www.postgresql.org/docs/9.5/static/sql-insert.html](https://www.postgresql.org/docs/9.5/static/sql-insert.html)

Командная оболочка cmder

[http://cmder.net/](http://cmder.net/)

Настроить Perfomance Counets

[http://www.npgsql.org/doc/performance.html\#performance-counters](http://www.npgsql.org/doc/performance.html#performance-counters)

Сакура фреймворк

[https://github.com/oxalorg/sakura](https://github.com/oxalorg/sakura)

Использование окна C\# Interactive

Проверка группы строк на идентиность.

[https://stackoverflow.com/questions/8094867/good-gethashcode-override-for-list-of-foo-objects-respecting-the-order](https://stackoverflow.com/questions/8094867/good-gethashcode-override-for-list-of-foo-objects-respecting-the-order)

[https://stackoverflow.com/questions/263400/what-is-the-best-algorithm-for-an-overridden-system-object-gethashcode?noredirect=1&lq=1](https://stackoverflow.com/questions/263400/what-is-the-best-algorithm-for-an-overridden-system-object-gethashcode?noredirect=1&lq=1)

[https://stackoverflow.com/questions/10567450/implement-gethashcode-for-objects-that-contain-collections](https://stackoverflow.com/questions/10567450/implement-gethashcode-for-objects-that-contain-collections)

Какое исключение нужно бросать в свиче по енуму

[https://stackoverflow.com/questions/3349540/throwing-exceptions-in-switch-statements-when-no-specified-case-can-be-handled](https://stackoverflow.com/questions/3349540/throwing-exceptions-in-switch-statements-when-no-specified-case-can-be-handled)

[https://stackoverflow.com/questions/13645149/what-is-the-correct-exception-to-throw-for-unhandled-enum-values](https://stackoverflow.com/questions/13645149/what-is-the-correct-exception-to-throw-for-unhandled-enum-values)

Использование делегатов с ковариантными/контрвариантными интерфейсами

Как работают аннотации таблиц, которые использует DynamicFilters

[https://romiller.com/2017/02/14/ef-core-1-1-read-only-entities-extending-metadata-with-annotations/](https://romiller.com/2017/02/14/ef-core-1-1-read-only-entities-extending-metadata-with-annotations/)

[https://stackoverflow.com/questions/48210091/how-to-access-the-ef-model-annotations-in-migration-class-up-method](https://stackoverflow.com/questions/48210091/how-to-access-the-ef-model-annotations-in-migration-class-up-method)

[https://msdn.microsoft.com/en-us/library/system.data.entity.migrations.dbmigration.createtable\(v=vs.113\).aspx](https://msdn.microsoft.com/en-us/library/system.data.entity.migrations.dbmigration.createtable%28v=vs.113%29.aspx)

[https://github.com/zzzprojects/EntityFramework.DynamicFilters/issues/90](https://github.com/zzzprojects/EntityFramework.DynamicFilters/issues/90)

Для вызова c\# Interactive на моём коде

[https://stackoverflow.com/questions/11135571/can-the-c-sharp-interactive-window-interact-with-my-code](https://stackoverflow.com/questions/11135571/can-the-c-sharp-interactive-window-interact-with-my-code)

Ограничения параметров типов class и операции == и !=

Скит написал, что в этом случае всегда проверяется ссылочная идентичность и не учитывается если эти операции

перегружены, как например в string - то есть в случае со стринг будет проверка на ссылочную идентичность

Тестирование производительности в .net

[https://github.com/dotnet/BenchmarkDotNet](https://github.com/dotnet/BenchmarkDotNet)

[https://benchmarkdotnet.org/Overview.htm](https://benchmarkdotnet.org/Overview.htm)

Использование **StringComparison.Ordinal **or **StringComparison.OrdinalIgnoreCase**

[https://msdn.microsoft.com/en-us/library/ms973919.aspx](https://msdn.microsoft.com/en-us/library/ms973919.aspx)

Попробовать поиграться с юникодом

* Создать строку из байтов
* Посмотреть юникодную строку в виде байтов и попробовать ее расшифровать

Следующая ошибка в Visual Studio

[https://stackoverflow.com/questions/1695040/visual-studio-jump-to-next-error-shortcut](https://stackoverflow.com/questions/1695040/visual-studio-jump-to-next-error-shortcut)

Насколько дорога операция typeof - бенчмарк тест

typeof\(IList&lt;CubeElementViewModel&gt;\) == modelType vs кэшированная версия - для биндера

**Тестирование производительности в PostgreSQL**

Пример замера производительности: [https://stackoverflow.com/questions/6633050/performance-difference-between-int4-and-int8-in-postgresql-on-64-bit-server](https://stackoverflow.com/questions/6633050/performance-difference-between-int4-and-int8-in-postgresql-on-64-bit-server)

Утилита для замеров производительности: [https://www.postgresql.org/docs/10/static/pgbench.html](https://www.postgresql.org/docs/10/static/pgbench.html)

Можно ли использовать Body в Get запросе / Что такое Get запрос

Частый вопрос на собеседовании Что такое Кластерный индекс

[https://stackoverflow.com/questions/4796548/about-clustered-index-in-postgres](https://stackoverflow.com/questions/4796548/about-clustered-index-in-postgres)

Во что разворачивается yeld return

Производительность nullable value type

