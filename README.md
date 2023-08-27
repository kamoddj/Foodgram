## Foodgram

Добро пожаловать в Foodgram. Тут вы можете выкладывать свои любимые рецепты. Делиться ими с друзьями и своими подписчиками. Можно в один клик скачать все нужные продукты и смело топать в магазин, ведь у вас на руках будет список с нужными продуктами любимых блюд.

Проект будет доступен по [адресу](http://free-foodgram.ddns.net)

### Технологии:

Python, Django, Django Rest Framework, Docker, Gunicorn, NGINX, PostgreSQL, Yandex Cloud

### Развернуть проект на удаленном сервере:

- Клонировать репозиторий:
```
git@github.com:kamoddj/foodgram-project-react.git
```

- Скопировать на сервер файлы docker-compose.yml, nginx.conf из папки infra.

-Запустить контейнеры Docker, выполнить команду на сервере

```
sudo docker compose up -d
```

- Выполнить миграции:
```
sudo docker compose exec backend python manage.py migrate
```

- Создать суперпользователя:
```
sudo docker compose exec backend python manage.py createsuperuser
```

- Собрать статику:
```
sudo docker compose exec backend python manage.py collectstatic --noinput
```

- Наполнить базу данных содержимым из файла ingredients.json:
```
sudo docker compose exec backend python manage.py loaddata ingredients.json
```

### После каждого обновления репозитория (push в ветку master) будет происходить:

1. Проверка кода на соответствие стандарту PEP8
2. Сборка и доставка докер-образов frontend и backend на Docker Hub
3. Разворачивание проекта на удаленном сервере
4. Отправка сообщения в Telegram в случае успеха