### Foodgram

Добро пожаловать в продуктовый помощник [Foodgram](http://free-foodgram.ddns.net). Тут ты можешь делить своими любимыми рецпатами с друзьями и подписчиками. Добавлять понравившиеся рецепты в избранное и смело топать в магазин за покупками, так как у тебя на руках уже будет список со всеми нужными продуктами. 

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

- Собрать статику:
```
sudo docker compose -f docker-compose.yml exec backend python manage.py collectstatic --no-input
```

- Наполнить базу данных содержимым из файла ingredients.json:
```
sudo docker compose exec backend python manage.py loaddata ingredients.json
```

## Через Git Action настроена автоматизация, после git push в ветку master. Тебе останеться лишь создать суперюзера.
```
sudo docker compose exec backend python manage.py createsuperuser
```