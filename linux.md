# Linux

Очистка диска от данных: [https://wiki.archlinux.org/index.php/Securely\_wipe\_disk](https://wiki.archlinux.org/index.php/Securely_wipe_disk)

```text
shred -v /dev/sd # очистить диск
shred -v file1.txt file2.jpg file3.doc # очистить указанные файлы
```

Больше про shred: [https://www.computerhope.com/unix/shred.htm](https://www.computerhope.com/unix/shred.htm)

## Хоткеи bash

### Working With Processes

Ctrl+C: Interrupt \(kill\) the current foreground process running in in the terminal. This sends the SIGINT signal to the process, which is technically just a request—most processes will honor it, but some may ignore it.

Ctrl+Z: Suspend the current foreground process running in bash. This sends the SIGTSTP signal to the process. To return the process to the foreground later, use the fg process\_name command.

Ctrl+D: Close the bash shell. This sends an EOF \(End-of-file\) marker to bash, and bash exits when it receives this marker. This is similar to running the exit command.

### Controlling the Screen

Ctrl+L: Clear the screen. This is similar to running the “clear” command.

Ctrl+S: Stop all output to the screen. This is particularly useful when running commands with a lot of long, verbose output, but you don’t want to stop the command itself with Ctrl+C.

Ctrl+Q: Resume output to the screen after stopping it with Ctrl+S.

### Moving the Cursor

Ctrl+A or Home: Go to the beginning of the line.

Ctrl+E or End: Go to the end of the line.

Alt+B: Go left \(back\) one word.

Ctrl+B: Go left \(back\) one character.

Alt+F: Go right \(forward\) one word.

Ctrl+F: Go right \(forward\) one character.

Ctrl+XX: Move between the beginning of the line and the current position of the cursor. This allows you to press Ctrl+XX to return to the start of the line, change something, and then press Ctrl+XX to go back to your original cursor position. To use this shortcut, hold the Ctrl key and tap the X key twice.

### Deleting Text

Ctrl+D or Delete: Delete the character under the cursor.

Alt+D: Delete all characters after the cursor on the current line.

Ctrl+H or Backspace: Delete the character before the cursor.

Fixing Typos

Alt+T: Swap the current word with the previous word.

Ctrl+T: Swap the last two characters before the cursor with each other. You can use this to quickly fix typos when you type two characters in the wrong order.

Ctrl+\_: Undo your last key press. You can repeat this to undo multiple times.

### Cutting and Pasting

Ctrl+W: Cut the word before the cursor, adding it to the clipboard.

Ctrl+K: Cut the part of the line after the cursor, adding it to the clipboard.

Ctrl+U: Cut the part of the line before the cursor, adding it to the clipboard.

Ctrl+Y: Paste the last thing you cut from the clipboard. The y here stands for “yank”.

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

```text
cat filename | less 
cat Filename | pg 
cat Filename | more
cat sample | grep -v a | sort - r
```

## Утилиты командной строки

Статья про утилиты работающие с текстом: [https://www.tecmint.com/linux-file-operations-commands/](https://www.tecmint.com/linux-file-operations-commands/)

### grep

Регулярки: [https://www.guru99.com/linux-regular-expressions.html](https://www.guru99.com/linux-regular-expressions.html)

```bash
tecmint@TecMint ~ $ grep "aaronkilik" /etc/passwd
aaronkilik:x:1001:1001::/home/aaronkilik:

tecmint@TecMint ~ $ cat /etc/passwd | grep "aronkilik"
aaronkilik:x:1001:1001::/home/aaronkilik:
```

### less

### ps

```bash
ps ux # Все процессы запущенные под текущим пользователем
ps aux # Все процессы запущенные под всеми пользователями
```

### history

```text
history # выводить список последних команд в истории
history | grep cd # поиск в истории
!8 # выполнить восьмой номер в истории
```

Ctrl+r - поиск в истории, повторное нажатие перейти к следующему найденному, Enter - ввести команду.

Ctrl+s - перейти к предыдущему найденному пункту в истории.

Alt+r - если в команду полученную из историю внесли изменения и хочется их отменить.

#### Поиск в истории, если начал набирать часть команды, но понял, что она есть в истории

1. Перейти в начало строки \(Ctrl+a\)
2. Нажать Ctrl+r \(это начнёт поиск в истории и скоприует в буфер обмена всё что после курсора\)
3. Нажать Ctrl+y - это введёт набранную команду в поиск из буфера обмена
4. Нажимая Ctrl+r можно передвигаться назад в истории

[Куча все про историю и работу с ней](https://www.digitalocean.com/community/tutorials/how-to-use-bash-history-commands-and-expansions-on-a-linux-vps)

## Работа с сервисами

### Создание сервиса

[Основная статья](https://docs.microsoft.com/ru-ru/aspnet/core/host-and-deploy/linux-nginx?view=aspnetcore-2.2#monitor-the-app)

```bash
sudo nano /etc/systemd/system/kestrel-helloapp.service
```

```text
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

```text
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

$ sudo journalctl -fu ssh # Просмотр журнала ssh
```

В конфиге ssh клиента можно указать какой ключ использовать для определённого клиента

Редактируем \`~/.ssh/config\`

```text
Host server1.nixcraft.com
  IdentityFile ~/backups/.ssh/id_dsa
Host server2.nixcraft.com
  IdentityFile /backup/home/userName/.ssh/id_rsa
```

### Правим конфиг сервера

Предварительно сделать копию конфига

```bash
sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.original
sudo chmod a-w /etc/ssh/sshd_config.original
```

### Если не пускает под root по SSH

```bash
passwd root # У рута должен быть пароль
```

Редактируем конфиг /etc/ssh/sshd\_config

```text
PermitRootLogin yes
PermitRootLogin prohibit-password # Запретить вход по паролю, но оставить по ключу
```

Перезапускаем сервис

```bash
sudo systemctl restart ssh || systemctl restart sshd || systemctl restart sshd.service
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

