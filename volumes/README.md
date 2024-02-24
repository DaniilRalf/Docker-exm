Используется для соханения файлов не внутри контейнера а на локальной машине, для того,точбы при перезапуске контейнера у нас не утерялись данные
___


```
docker volume ls               (ПОСМОТРЕТЬ ВЕ ВОЛЬЮМЫ)
docker volume rm <volume_name> (УДАЛИТЬ ВОЛЬЮМ)
...
```
---
### 1 вариант (Host Volume)
Говорим что содержимое для nginx директории(ПРАВОЙ) будет хранитьсо локально в указаной директории(ЛЕВОЙ)
```
docker run -d --name web01 -p 80:80 -v /docker_volumes_test/nginx:/usr/share/nginx/html nginx
```
---
### 2 вариант (Anonimous Volume) (не рекомендуется)
Тоже самое что и выше, только он создает вольюм в кеше докера, в папке-хеше `var/lib/docker/volumes`
Возможно к этим файлам не будет доступа, поэтому `sudo ls -al var/lib/docker/volumes`
После удаления контейнера,вольюм удаляется
```
docker run -d --name web01 -p 80:80 -v /usr/share/nginx/html nginx
```
---
### 3 вариант (Named Volume) (самая распростаренная)
asdasdТоже самое что и выше, только он создает вольюм в кеше докера, в именной папке `var/lib/docker/volumes`
Возможно к этим файлам не будет доступа, поэтому `sudo ls -al var/lib/docker/volumes`
После удаления контейнера, вольюм не удаляется
```
docker run -d --name web01 -p 80:80 -v web_data:/usr/share/nginx/html nginx
```
