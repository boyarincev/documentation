# Visual Studio Code

## Создать и запустить консольное приложение

{% embed url="https://docs.microsoft.com/ru-ru/dotnet/core/tutorials/with-visual-studio-code" %}

```text
dotnet new console
dotnet run
```

## Добавление нугет-пакета в проект

```text
dotnet add package Newtonsoft.Json
```

Подробнее в статье

{% embed url="http://www.hanselman.com/blog/TryingOutDotnetNewTemplateUpdatesAndCsprojWithVS2017.aspx" %}

Другие варианты установки

{% embed url="https://stackoverflow.com/q/40675162/5402731" %}

## Запуск в релизе

```text
dotnet build -c release //собрать в релизе
dotnet run -c release //запустить в релизе
```

Источник

{% embed url="https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-build" %}

Другие варианты

{% embed url="https://stackoverflow.com/q/47854962/5402731" %}





