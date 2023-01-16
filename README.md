# Установка Docker 
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



# Основные команды
Просмотр всех образов
```shell
sudo docker images
```
Просмотр всех контейнеров
```shell
sudo docker ps
```
18:35
