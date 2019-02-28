# Linux \(Ubuntu\)

Очистка диска от данных: [https://wiki.archlinux.org/index.php/Securely\_wipe\_disk](https://wiki.archlinux.org/index.php/Securely_wipe_disk)

```
shred -v /dev/sd # очистить диск
shred -v file1.txt file2.jpg file3.doc # очистить указанные файлы
```

Больше про shred: [https://www.computerhope.com/unix/shred.htm](https://www.computerhope.com/unix/shred.htm)

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

Основная статья: [https://www.guru99.com/linux-redirection.html](https://www.guru99.com/linux-redirection.html)

```bash
ls -al > listings # Перенаправление вывода STDOUT в файл
ls -al >> listings 
# Перенаправление вывода STDOUT в файл, данные будут дописываться в конец файла, а не перезаписывать его полностью
Mail -s "Subject" to-address < Filename # Перенаправление ввода STDIN из файла
```

Перенаправления работают с файлами, а в Линуксе всё является файлом, поэтому перенаправления можно делать и на устройства - они тоже являются файлами.

Каждый файл имеет его Файловый Дескриптор. Когда команда запускается в терминале всегда существуют три файла: стандартный ввода, стандартный вывод, стандартные ошибки, эти файлы имеют следующие файловые дескрипторы:

|  |  |
| :--- | :--- |
| Стандартный ввод STDOUT | 0 |
| Стандартный вывод STDIN | 1 |
| Стандартные ошибки STDERR | 2 |

По-умолчанию эти файлы подключены к терминалу. К этим фйловым дескрипторам можно обращаться, чтобы перенаправить их в другие файлы.

```bash
find . -name 'my*' 2>error.log # Перенаправить ошибки в файл
ls Documents ABC> dirlist 2>&1 # Перенаправить вывод в файл, а ошибки туда же куда вывод
ls Documents ABC 2>&1 >dirlist # Перенаправить ошибки туда куда сейчас направлен вывод (консоль), а вывод в файл
```

#### Pipe's

Перенаправления работают с файлами, если же нужно напрямую соединить вывод одной команды и вход другой, то для этого нужно использовать pipe.

```
cat filename | less 
cat Filename | pg 
cat Filename | more
cat sample | grep -v a | sort - r
```

## Утилиты командной строки

### grep

Регулярки: https://www.guru99.com/linux-regular-expressions.html

### less



### ps

```bash
ps ux # Все процессы запущенные под текущим пользователем
ps aux # Все процессы запущенные под всеми пользователями
```

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

## Firewall \(ufw\)

```bash
sudo apt-get install ufw

sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp

# или

sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https

sudo ufw allow from any to any port 10000 proto tcp
sudo ufw allow from 10.1.1.231 to any port 443 proto tcp
sudo ufw allow from 10.1.1.0/8 to any port 53 proto udp
sudo ufw allow from any to any port 20,21 proto tcp

sudo ufw enable

sudo ufw status # вывести все текущие правила
sudo ufw status verbose # видимо какой-то более расширенный вывод

sudo ufw status numbered # вывести правила с номерами
sudo ufw delete  5 # удалить правило по номеру
```

## Fail2Ban

[Основная статья](https://community.vscale.io/hc/ru/community/posts/211756429-Использование-fail2ban-для-защиты-SSH-от-подбора-пароля) по установке и настройке

```
sudo service fail2ban restart # перезапуск сервиса
tail -n 20 -f /var/log/fail2ban.log # просмотр логов
```

## Работа с SSH

```bash
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com" # Генерация ключа
$ ssh-copy-id username@remotehost # Копирование на удалённый компьютер

$ sudo systemctl status ssh # узнать состояние ssh сервера

$ ssh -i /path/to/id_rsa user@server.nixcraft.com # подключение по ssh с явным указанием ключа
# (по-умолчанию используется ключ с названием id_rsa)
```

В конфиге ssh клиента можно указать какой ключ использовать для определённого клиента

Редактируем \`~/.ssh/config\`

```
Host server1.nixcraft.com
  IdentityFile ~/backups/.ssh/id_dsa
Host server2.nixcraft.com
  IdentityFile /backup/home/userName/.ssh/id_rsa
```

### Если не пускает под root по SSH

```bash
passwd root # У рута должен быть пароль
```

Редактируем конфиг /etc/ssh/sshd\_config

```
PermitRootLogin yes
```

Перезапускаем сервис

```bash
systemctl restart ssh || systemctl restart sshd
```

### Статьи

[Генерация ключа](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

[Просмотр существующих ключей](https://help.github.com/en/articles/checking-for-existing-ssh-keys)

[Настройка ssh на Ubuntu](https://help.ubuntu.com/lts/serverguide/openssh-server.html.en)

[Очень подробно про настройку конфига](https://www.ssh.com/ssh/sshd_config/)

[Как добавить ssh ключи в Putty](https://support.rackspace.com/how-to/log-into-a-linux-server-with-an-ssh-private-key-on-windows/)

[Статья в которой описывается создание ключа и его копирование на сервер](https://www.digitalocean.com/community/tutorials/ssh-ubuntu-18-04-ru)

## Создание пользователя

```bash
adduser username # создать пользователя
usermod -aG sudo username # включить в группу sudo 
#по-умолчанию на Ubuntu пользователи состоящие в этой группе имеют sudo привилегии
su - username # сменить пользователя на нового
```

## Midnight Commander

### Создать архив tar.gz

Можно сделать с помощью mc - есть пункт в меню появляющийся при нажатии на F2 - сожмёт всю директорию в которой сейчас находимся.

### Работа с текстовым редактором

Хоткеи текстового редактора: [https://midnight-commander.org/wiki/doc/editor/hotkeys](https://midnight-commander.org/wiki/doc/editor/hotkeys)

## SCP

```bash
$ scp username@from_host:file.txt /local/directory/ # копируем файл с удалённого хоста на локальный
$ scp file.txt username@to_host:/remote/directory/ # копируем файл с локального хоста на удалённый
$ scp -r username@from_host:/remote/directory/  /local/directory/ # копируем директорию с удалённого хоста на локальный
$ scp -r /local/directory/ username@to_host:/remote/directory/$ scp username@from_host:/remote/directory/file.txt username@to_host:/remote/directory/
$ # копируем директорию с удалённого хоста на удалённый
$ scp -i ~/.ssh/id_rsa file username@to_host:/remote/directory 
$ # с указанием ключа, который нужно использовать при подключении
```



