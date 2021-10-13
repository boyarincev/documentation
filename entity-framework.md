# Entity Framework

## Change Tracking

Можно изменить стратегию отслеживания изменений, так чтобы не происходило сравнение всех данных в контексте с их копиями

[https://blog.oneunicorn.com/2016/11/16/notification-entities-in-ef-core-1-1/](https://blog.oneunicorn.com/2016/11/16/notification-entities-in-ef-core-1-1/)

[https://docs.microsoft.com/en-us/dotnet/api/microsoft.entityframeworkcore.changetrackingstrategy?view=efcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/microsoft.entityframeworkcore.changetrackingstrategy?view=efcore-2.1)

## Работа с отсоединёнными сущностями

1. Свойство с состоянием объекта: Unchanged, Added, Modified, Deleted
2. Идея: использовать именованные конструкторы для того чтобы выделить конструктор конструирования из БД.
3. Добавить метод добавления в чейнджтрекер, который автоматом будет проставлять имя свойства (при вызове из свойства).
4. Если у сущности состояние Added, то изменение свойств не должно приводить к измению состояния на Modified.
5. Сложный момент с удалением сущностей из коллекций или удалением сущностей на которые ссылаемся - помечаем их как удалённые, но должны ли они продолжать быть доступны по обычным ссылкам из доменного объекта в памяти
