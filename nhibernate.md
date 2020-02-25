# NHibernate

[Много всякой информации по маппингам и запросам, собранной вместе](https://habrahabr.ru/post/265371/)

## Настройка маппинга сущностей

* cascade="none" - значение по умолчанию. Hibernate будет игнорировать ассоциации, поэтому разруливать зависимости придется самостоятельно.
* cascade="save-update" говорит Hibernate'у, что разруливать зависимости необходимо при комите транзакции в которой делается save\(\) или update\(\) объекта. Суть разруливания заключается в том, что новые объекты, с которыми есть ассоциации у нашего, будут сохранены до него. Это позволяет обойти constraint-violations.
* cascade="delete" говорит Hibernate'у, что надо разруливать зависимости при удалении объекта.
* cascade="all" обозначает выполнение каскадных операций при save-update и delete.
* cascade="all-delete-orphan" обозначает то же самое, что и cascade="all", но к тому же Hibernate удаляет любые связанные сущности, удаленные из ассоциации \(например, из коллекции\).
* cascade="delete-orphan" обозначает, что Hibernate будет удалять любые сущности, которые были удалены из ассоциации.

[Источник](http://samolisov.blogspot.com/2009/02/hibernate.html)

## Fetch Strategies

[Описывается как загружать связанные сущности](http://blog.raffaeu.com/archive/2014/07/04/nhibernate-fetch-strategies.aspx) [Fetch vs FetchMany difference](http://stackoverflow.com/questions/4394692/fetch-vs-fetchmany-in-nhibernate-linq-provider) [Проблема с дублирующимися записями при FetchMany и затем ThenFetchMany](http://stackoverflow.com/questions/6194734/nhibernate-thenfetchmany-is-retrieving-duplicate-children)

## Fluent NHibernate

[How to work with Fluence NHibernate](http://www.infoworld.com/article/3030212/application-development/how-to-work-with-fluent-nhibernate-in-c.html) [Fluent NHibernate Getting Started](https://github.com/jagregory/fluent-nhibernate/wiki/Getting-started)

## Queries

[http://www.martinwilley.com/net/code/nhibernate/query.html](http://www.martinwilley.com/net/code/nhibernate/query.html) [http://www.martinwilley.com/net/code/nhibernate/query2.html](http://www.martinwilley.com/net/code/nhibernate/query2.html)

