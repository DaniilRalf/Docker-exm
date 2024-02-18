## 33:57

Статус сервиса
```shell
service docker status
```
Скачивание image
```shell
docker pull <image_name>
```
Запуск или скачивание и запуск image и запуск контейнера
```shell
docker run <image_name>
```
---

Проверка контейнеров
```shell
docker ps       (РАБОТАЮЩИХ)
docker ps -a    (ВСЕХ) 
```
Удаление контейнеров
```shell
docker rm <name or container_id>
```
----
Проверка образов
```shell
docker images    (ВСЕХ) 
```
Удаление образов
```shell
docker rmi <immage_id>
```
