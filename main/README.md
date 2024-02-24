## 1:37:00

---
## Общее

Статус сервиса
```shell
service docker status
```
Скачивание image
```shell
docker pull <image_name>
```
Запуск или (скачивание и запуск image) \
Результатом запуска images - является создание и запуск контейнера
```shell
docker run <image_name>                 (СТАНДАРТ)
docker run <image_name> echo "test"    (С ПОСЛЕДУЮЩИМ ЗАПУСКОМ КОМАНЛЫ)
docker run -d <image_name>              (НЕ ЗАНИМАЯ КОНСОЛЬ)
docker run --name <name> <image_name>   (С УКАЗАНИЕМ КОНКРЕТНОГО ИМЕНИ)
docker run --rm <image_name>            (СРАЗУ УДАЛЯТЬ КОНТЕЙНЕР КАК ОСТАНОВИТЬСЯ)
docker start <container_id>             (ЗАПУСК СОЗДАННОГО НО НЕ РАБОТАЮЩЕГО КОНТЕЙНЕРА)
```
---
## Контейнеры

Проверка контейнеров
```shell
docker ps                               (ПРОВЕРКА РАБОТАЮЩИХ)
docker ps -a                            (ПРОВЕРКА ВСЕХ)
```
Удаление контейнеров
```shell
docker stop <name or container_id> (ОСТАНОВИТЬ КОНТЕЙНЕР)
docker kill <name or container_id> (ОСТАНОВИТЬ КОНТЕЙНЕР)
docker rm <name or container_id>   (УДАЛИТЬ МОЖНО ТОЛЬКО НЕ РАБОТАЮЩИЙ КОНТЕЙНЕР)
```

Инспектирование контейнеров
```shell
docker inspect <name or container_id>   (ВСЯ ИНФА О КОНТЕЙНЕРЕ)
docker stats <name or container_id>     (СКОЛЬКО РЕСУРСОВ ПОТРЕБЛЯЕТ КОНТЕЙНЕР)
docker logs <name or container_id>      (ЛОГИ КОНТЕЙНЕРА)
docker logs -f <name or container_id>   (ЛОГИ КОНТЕЙНЕРА В ЛАЙВЕ)
docker exec -it <name or container_id> /bin/bash/  (ЗАЙТИ ВНУТРЬ КОНТЕЙНЕРА)
docker exec -it -u <name or container_id> /bin/bash/  (ЗАЙТИ ВНУТРЬ КОНТЕЙНЕРА С ПРАВАМИТЕКУЩЕГО ПОЛЬЗОВАТЕЛЯ)
```
----
## Образы

Проверка образов
```shell
docker images    (ВСЕХ) 
```
Удаление образов
```shell
docker rmi <immage_id>
```
