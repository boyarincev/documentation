# Linux

Очистка диска от данных: [https://wiki.archlinux.org/index.php/Securely\_wipe\_disk](https://wiki.archlinux.org/index.php/Securely_wipe_disk)

```
shred -v /dev/sd # очистить диск
shred -v file1.txt file2.jpg file3.doc # очистить указанные файлы
```

Больше про shred: https://www.computerhope.com/unix/shred.htm

## Управление процессами

### Запуск в фоне

```bash
 count & # запуск программы в фоне
 jobs # список работающих в
 fg # перевести из фонового режима в активный программу (если выполняется в фоне только одна)
 fg %# # перевести задачу с указанным номером джоба в активный режим
 kill PID # убить фоновый процесс по PID
 jobs -l # вывести список джобов с их PID'ами
 count 2> /dev/null & 
 # в фоне программа продолжить писать output и erros в консоль, перенаправить ошибки консоли в /dev/null
 count > /dev/null 2>$1 & # ошибки и вывод в /dev/null
 count 2>&1 > /dev/null # ошибки в консоль, вывод в /dev/null
```

#### Переводим запущенную программу в фон

```bash
# приостанавливаем выполнение программы  Ctrl-z
jobs # выводим список джобов
bg %# возобновляем работу программу в фоне
```

#### Перенаправления Ввода Вывода

Основная статья: https://www.guru99.com/linux-redirection.html

## Работа с сервисами

### Создание сервиса

[Основная статья](https://docs.microsoft.com/ru-ru/aspnet/core/host-and-deploy/linux-nginx?view=aspnetcore-2.2#monitor-the-app)

```bash
sudo nano /etc/systemd/system/kestrel-helloapp.service
```

```ini
[Unit]
Description=Example .NET Web API App running on Ubuntu

[Service]
WorkingDirectory=/var/www/helloapp
ExecStart=/usr/bin/dotnet /var/www/helloapp/helloapp.dll
Restart=always
# Restart service after 10 seconds if the dotnet service crashes:
RestartSec=10
KillSignal=SIGINT
SyslogIdentifier=dotnet-example
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production
Environment=DOTNET_PRINT_TELEMETRY_MESSAGE=false
# The default value is 90 seconds for most distributions.
# TimeoutStopSec=90

[Install]
WantedBy=multi-user.target
```

### Управление сервисами

```bash
sudo systemctl enable kestrel-helloapp.service #включение сервиса
sudo systemctl start kestrel-helloapp.service #старт сервиса
sudo systemctl status kestrel-helloapp.service #просмотр статуса сервиса
```

### Просмотр журнала сервиса

```bash
sudo journalctl -fu kestrel-helloapp.service
sudo journalctl -fu kestrel-helloapp.service --since "2016-10-18" --until "2016-10-18 04:00"
sudo journalctl -fu kestrel-helloapp.service --since today --until 1 hour ago
```

## Firewall

```bash
sudo apt-get install ufw

sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp

sudo ufw enable
```

## Fail2Ban

[Основная статья](https://community.vscale.io/hc/ru/community/posts/211756429-Использование-fail2ban-для-защиты-SSH-от-подбора-пароля)

## Работа с SSH

```bash
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com" # Генерация ключа
$ ssh-copy-id username@remotehost # Копирование на удалённый компьютер
```

### Статьи

[Генерация ключа](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

[Просмотр существующих ключей](https://help.github.com/en/articles/checking-for-existing-ssh-keys)

[Настройка ssh на Ubuntu](https://help.ubuntu.com/lts/serverguide/openssh-server.html.en)