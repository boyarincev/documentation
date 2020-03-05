# Docker

```bash
sudo docker exec -it data-collection /bin/sh
sudo docker images
psql -h localhost -p 5432 -U postgres
sudo docker run  -v /home/boyarincev/data-collection-share:/mnt/volume --rm -p 8090:6634 --name data-collection_sample -e "BASIC_IP=192.168.23.146" -e "HTTPS=false" data-collection:latest
sudo docker stop  data-collection_sample
sudo docker build -t data-collection:CLang -f installer/docker/dockerfile --build-arg=VERSION=2.13.1 .
sudo docker build -t baseenv .

sudo docker ps -a // запущенные и не запущенные контейнеры
sudo docker stop имя_контейнера //остановить контейнерs

sudo docker logs -f имя_контейнера //следить за логами контейнера
```

