Собрать image на основании докер-файла
```shell
docker build .                              (БАЗОВЫЙ)
docker build -t <image_name>:<image_tag> .  (С УКАЗАНИЕМ ИМЕНИ И ТЭГА)
```

Установить уже созданному образу Тэг и Имя
```shell
docker tag <image_id> <image_name_new>:<image_tag_new>
```

Стандартная команда запуска контейнера
```shell
docker run --rm --name=<container_name> <image_name>:<tag>
```