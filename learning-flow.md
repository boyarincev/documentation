# Learning Flow

### Утечки памяти в Javascript

* [x] [Best practices for reducing Garbage Collector activity in Javascript](https://stackoverflow.com/questions/18364175/best-practices-for-reducing-garbage-collector-activity-in-javascript) - много советов как избежать сборку мусора
* [ ] [Javascript and Garbage collection](https://stackoverflow.com/questions/18800440/javascript-and-garbage-collection) - небольшой ответ про то как избегать сборки мусора

* [x] [**Memory Management**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management)** в Javascript - Must Read, статья с MDN**

* [x] [**Concurrency model and Event Loop in Javascript**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)** - Must Read, статья с MDN**

### Javascript

* [ ] [Iterators and generators in Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators) - MDN
* [ ] [Побитовые операции](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators)
* [ ] [Рефакторинг салона видеопроката на JavaScript](https://habrahabr.ru/post/320280/)

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

### Архитектура

* [ ] [CQRS. Факты и заблуждения](https://habrahabr.ru/post/347908/)
* [ ] [Строим распредёленное реактивное приложение и решаем задачи согласованности](https://habrahabr.ru/company/2gis/blog/348510/)

* [ ] [Эталонное приложение на базе контейнеров и архитектуры микросервисов](https://habrahabr.ru/company/microsoft/blog/346746/)

* [ ] [Domain Driven Design на практике](https://habrahabr.ru/post/334126/)

### Сsharp

* [ ] [Исследуем сопоставление с образцом в C\# 7](https://habrahabr.ru/post/347916/)

### Профилирование приложений

* [ ] [CodeTrack](https://getcodetrack.wordpress.com/)

### Верстка

* [ ] [Современный CSS для динозавров](https://habrahabr.ru/post/348500/)
* [ ] [**sakura**](https://github.com/oxalorg/sakura) - минималистичный css фреймворк
* [ ] [30 секунд CSS](https://habrahabr.ru/company/mailru/blog/350160/)

### WEB

* [ ] [Учебник HTTP на MDN](https://developer.mozilla.org/ru/docs/Web/HTTP)
* [ ] [CORS на MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)

### Математика

* [ ] [Как читать математику](https://habrahabr.ru/post/346228/)

### Производительность БД

* [ ] [Три аспекта оптимизации \(БД и ПО\)](https://habrahabr.ru/post/349910/)

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

