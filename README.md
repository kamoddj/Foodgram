### Foodgram

Добро пожаловать в продуктовый помощник Foodgram. Тут ты можешь делить своими любимыми рецпатами с друзьями и подписчиками. Добавлять понравившиеся рецепты в избранное и смело топать в магазин за покупками, так как у тебя на руках уже будет список со всеми нужными продуктами. 

### Что бы развернуть проект на сервере тебе понадобиться:

- Клонировать репозиторий:
```
git clone git@github.com:kamoddj/foodgram-project-react.git
```

- Скопировать на сервер файлы docker-compose.yml, nginx.conf из папки infra

- Создать и запустить контейнеры Docker, выполнить команду на сервере
```
sudo docker compose up -d
```

- После успешной сборки выполнить миграции:
```
sudo docker compose exec backend python manage.py migrate
```

- Создать суперпользователя:
```
sudo docker compose exec backend python manage.py createsuperuser
```

- Наполнить базу данных содержимым из файла ingredients.json:
```
sudo docker compose exec backend python manage.py loaddata ingredients.json
```