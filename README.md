# Running the Application

1. Структура проекта.
  service-a/
├── Http/
...
  service-b/
├── Http/
...
  docker-compose.yml
2. git clone каждого сервиса и docker-compose
3. в env.example service-b указываем SERVICE_A_URL=http://172.17.0.1:8001, где хост ваш докер-хост (ip addr show docker0)
4. в директории с docker-compose файлом: docker-compose up --build
5. docker ps проверяем контейнеры
6. для работы с очередями docker exec -it micro-pet-service2-1 php artisan user:listen (micro-pet-service2-1 название контейнера service-b)
  