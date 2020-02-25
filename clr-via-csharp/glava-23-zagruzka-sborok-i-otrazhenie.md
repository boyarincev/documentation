---
book: 'CLR via C#'
tags: synopsis
---

# Глава 23. Загрузка сборок и отражение

Загрузить сборку в домен

```text
Assembly.Load(...)
```

## Использование отражения для создания динамически расширяемых приложений

Методы из System.Reflection по факту работают с таблицами метаданных, они представляют объектную модель для работы с метаданными программы.

## Производительность отражения

Отражение работает медленно.

Вызов метода или обращения к свойству через отражение работает медленно.

**Есть обходной путь**

Можно с помощью отражения создать объект, затем привести его либо к базовому типу, либо интерфейсу и вызывать методы, обращаться к свойства, полям через эти объекты, а не через отражение.

## Типы определённые в сборке

```text
Assembly a = Assembly.Load(...);
a.ExportedTypes;
```

Type - это ссылка на тип, он содержит минимум информации

```text
object.GetType();
```

Более полная информация содержится в TypeInfo

```text
using System.Reflection.IntrispectionExtensions

Type type = object.GetType();
TypeInfo typeInfo = type.GetTypeInfo();
```

Получение TypeInfo - более тяжёлая операция, чем получение Type.

## Создание экземпляров типа

Используя тип Type можно создать экземпляр этого типа

```text
//Статические методы
System.Activator.CreateInstance(...); //передаёт Type
System.Activator.CreateInstanceFrom();

//Экземплярные методы
appDomain.CreateInstance();
appDomain.CreateInstanceFrom();

// экземпляный метод Invoke из System.Reflection.ConstructorInfo (можно получить из TypeInfo)

//Создать массив
System.Array.CreateArray(...);

//Создать делегат
System.Delegate.CreateInstance(...);

//Создание обобщённого типа
Type openType = typeof(Dictionary<,>);
Type closeType = openType.MakeGenericType(int, int); //в параметре передаём массив тайпов закрытого обобщённого типа
Object o = Activator.CreateInstance(closeType);
```

## Создание приложений с поддержкой подключаемых компонентов

1. Определяем интерфейс от которого должны наследоваться подключаемые компоненты
2. Компоненты реализуют этот интерфейс
3. Ищем сборки в папке и грузим их
4. В сборке ищем типы, которые можно привести к интерфейс определённому на первом шаге
5. Инстанцируем найденные компоненты

## Нахождение членов типа путём отражения

```text
AppDomain.CurrentDomain.GetAssemblies(); //Сборки в текущем домене
assembly.ExportedTypes //типы в сборке
type.GetTypeInfo().DeclaredMembers // члены типа
```

TypeInfo содержит много методов для получения конкретных типов члена

Иерархися членов типов.

Все члены типа иметют тип MemberInfo.

Реализовывать его могут:

* Type - вложенный тип
* FieldInfo - поле
* MethodInfo - метод
* ConstrucotrInfo
* PropertyInfo
* EventInfo

Последние четыре, также содержат метод GetParameterInfo\(\) и из него можно получить массив объектов ParameterInfo.

### Обращения к членам типов

FieldInfo - GetValue, SetValue

ConstructorInfo - Invoke

MethodInfo - Invoke

PropertyInfo - GetValue, SetValue

EventInfo - Add\(Remove\)EventHandler

#### Второй вариант обращения

Методы \(конструкторы, свойства и т.д.\) можно получить как делегаты и вызвать их.

```text
propertyInfo.SetMethod.CreateDelegate()
```

### Использование дескрипторов привязки для снижения потребления памяти процесса

Типы Type и MemberInfo занимают много места в памяти, поэтому вместо них можно использовать облегченные объекты занимающие меньше памяти.

```text
RuntimeTypeHandle
RuntimeFieldHandle
RuntimeMethodHandle
```

это значимые типы, содержащие только IntPtr - это дескриптор, ссылающийся на тип, поле или метод в куче загрузчика домена.

```text
runtimeTypeHanlde = Type.GetTypeHandle(type); // обращение к типу
runtimeFieldHandle = fieldInfo.FieldHandle; //обращение к экземпляру
fieldInfo = FieldInfo.GetTypeFromHandle(runtimeFieldHandle);
runtimeMethodHandle = methodInfo.MethodHandle;
methodInfo = MethodInfo.GetMethodFromHandle(runtimeMethodHandle);
```

