# Running the Application

1. Структура проекта.
```
    service-a/
  ├── Http/
  ...
    service-b/
  ├── Http/
  ...
    docker-compose.yml
```
3. git clone каждого сервиса и docker-compose
4. в env.example service-b указываем SERVICE_A_URL=http://172.17.0.1:8001, где хост ваш докер-хост (```ip addr show docker0```)
5. в директории с docker-compose файлом:
   ``` docker-compose up --build ```
6. проверяем контейнеры:
  ``` docker ps ```
7. запускаем миграции в каждом сервисе:
  ``` docker exec -it micro-pet-service1-1 php artisan migrate --force ``` (micro-pet-service1-1 название контейнера service-a)
  ``` docker exec -it micro-pet-service2-1 php artisan migrate --force ``` (micro-pet-service2-1 название контейнера service-b)
8. для работы с очередями:
    ``` docker exec -it micro-pet-service2-1 php artisan user:listen ``` (micro-pet-service2-1 название контейнера service-b)
  
