# Windows Server

## Безопасность

* Запретить входить под учёткой администратора, через удалённый рабочий стол
* Создать новую учётку для работы под ней

## Ограничение доступа через удалённый рабочий стол для Администратора

> Если в домене - то распространяете указанную ниже политику на все нужные компьютеры.
>
> Если домена нет - то ручками на каждом прописываем с помощью gpedit.msc:
>
> Конфигурация компьютера - Конфигурация Windows - Параметры безопасности - Локальные политики - Назначение прав пользователей - Запретить вход в систему через службы удаленных рабочих столов.
>
> Добавляете туда нужные учётные записи.
>
> Попутно можно давить эти учётные записи в другие ограничивающие группы:
>
> * Отказать в доступе к этому компьютеру из сети;
> * Запретить локальный вход (если эта учётная запись только для запуска служб, и локально под ней никто не работает).

{% embed url="https://toster.ru/q/303961" %}

## Проверка доступности ресурса гет-запросом

{% embed url="https://superuser.com/a/755581/538791" %}

### cURL

Windows 10 includes `curl.exe`:

[https://techcommunity.microsoft.com/t5/containers/-/ba-p/382409](https://techcommunity.microsoft.com/t5/containers/-/ba-p/382409)

so you can do something like this:

```bash
# example 1
curl.exe --output index.html --url https://superuser.com
# example 2
curl.exe -o index.html https://superuser.com
```

If you have older Windows, you can still download it:

[https://curl.haxx.se/windows](https://curl.haxx.se/windows)

### PowerShell

```bash
# example 1
Invoke-WebRequest -OutFile index.html -Uri https://superuser.com
# example 2
iwr -outf index.html https://superuser.com
```

[https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-webrequest)
