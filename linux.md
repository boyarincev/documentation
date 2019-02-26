# Linux

Очистка диска от данных: [https://wiki.archlinux.org/index.php/Securely\_wipe\_disk](https://wiki.archlinux.org/index.php/Securely_wipe_disk)

```
# shred -v /dev/sd
```

## Управление процессами



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
sudo systemctl enable kestrel-helloapp.service -- включение сервиса
sudo systemctl start kestrel-helloapp.service -- старт сервиса
sudo systemctl status kestrel-helloapp.service -- просмотр статуса сервиса
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

[Основная статья](https://community.vscale.io/hc/ru/community/posts/211756429-%D0%98%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-fail2ban-%D0%B4%D0%BB%D1%8F-%D0%B7%D0%B0%D1%89%D0%B8%D1%82%D1%8B-SSH-%D0%BE%D1%82-%D0%BF%D0%BE%D0%B4%D0%B1%D0%BE%D1%80%D0%B0-%D0%BF%D0%B0%D1%80%D0%BE%D0%BB%D1%8F)





