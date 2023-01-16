# Установка Docker 
(https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)\
Настройка пакетов, установка необходимфх зависимостей
```shell
sudo apt-get update
sudo apt-get install \
ca-certificates \
curl \
gnupg \
lsb-release
```
Добавьте официальный GPG-ключ Docker:
```shell
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
Hастройкa репозитория:
```shell
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
Обновление пакетов
```shell
sudo apt-get 
```
umask по умолчанию может быть неправильно настроен, что препятствует обнаружению файла открытого ключа репозитория. Попробуйте предоставить разрешение на чтение для файла открытого ключа Docker перед обновлением индекса пакета:
```shell
sudo chmod a+r /etc/apt/keyrings/docker.gpg
sudo apt-get 
```
Чтобы установить последнюю версию, запустите:
```shell
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
Убедитесь, что установка Docker Engine прошла успешно, запустив hello-worldобраз:
```shell
sudo docker run hello-world
```



# Структура
`Dockerfile` - файл где прописана спецификация образа
`.dockerignore` - файл где прописаны файлы не включаемые в образ



# Основные команды
### Просмотр всех образов
```shell
sudo docker images
```
### Просмотр всех контейнеров
```shell
sudo docker ps
sudo docker ps -a   -посмотреть все контейнеры даже те которые уже завершились
sudo docker ps -q   -посмотреть тейнертолько id всех контейнеров работающих(можно добавитьб -а)
```
Создать образ, при этом он автоматически создает образы в слоеный пирог которые прописаны в FROM
```shell
sudo docker build . -t <image-name>
```
Запуск образа с `-d` (если этот флаг убрать терминал будет занят, так лучше и делать) запускает контейнер в автономном режиме, 
оставляя контейнер работать в фоновом режиме. 
Флаг `-p` перенаправляет общедоступный порт на частный порт внутри контейнера.
```shell
sudo docker run -p 8001:8000 -d <name>
sudo docker run -p 8001:8000 -d <name> --rm   -после завершения контейнер сам удалиться (--rm)
```
### На этом моменте контейнер запущен
### (Дополиельно)
Посмотреть логи контейнера
```shell
sudo docker logs <container id>
```
Зайти внутрь контейнера
```shell
sudo docker exec -it <container id> /bin/bash
```


Остеановить
```shell
sudo docker stop $(sudo docker ps -aq)   -в скобках передаем команду смотреть выше, флагами управляем какие контейнеры удаляем
sudo docker stop <id>    -остановить конкретный контейнер
```
Удвлить
```shell
sudo docker rm $(docker ps -aq)   -в скобках передаем команду смотреть выше, флагами управляем какие контейнеры удаляем
sudo docker rm <id>    -удалить конкретный контейнер
```
Удвлить все образы
```shell
sudo docker rmi $(docker images -q)  -в скобках передаем команду смотреть выше, флагами управляем какие контейнеры удаляем
sudo docker rmi <id>    -удалить конкретный образ
```
УДалить все образы и контейнеры
```shell
sudo docker system prune
```

35:40