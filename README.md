# API для YATUBE

## Описание

API для YATUBE - это проект социальной сети, которая позволяет публиковать свои и комментировать чужие посты, а также подписываться (отписываться) на интересующих авторов.

## Как запустить проект

### Клонировать репозиторий:

git clone git@github.com:calyps0l/api_final_yatube.git

### Перейти в него с помощью командной строки:

cd api_yatube

### Создать и активировать виртуальное окружение:

python3 -m venv venv

source venv/bin/activate

### Установить все необходимые зависимости:

pip install -r requirements.txt

### Выполнить миграции:

python3 manage.py migrate

### Запустить проект:

python3 manage.py runserver

## Примеры работы с API для всех пользователей

GET api/v1/posts/ - получение списка всех публикаций

GET api/v1/posts/{id}/ - получение публикации по id

GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации

GET api/v1/{post_id}/comments/{id}/ - получение комментария к публикации по id

GET api/v1/groups/ - получение списка доступных сообществ

GET api/v1/groups/{id}/ - получение информации о сообществе по id

## Примеры работы с API для авторизированных пользователей


POST /api/v1/jwt/create/ - получение JWT-токена, который необходим для авторизации пользователя

Пример запроса:

{
"username": "string",
"password": "string"
}

POST /api/v1/jwt/refresh/ - обновление JWT-токена

POST /api/v1/jwt/verify/ - проверка JWT-токена

POST /api/v1/posts/ - создание публикации 

Пример запроса:

{
"text": "string",
"image": "string",
"group": 0
}

PUT /api/v1/posts/{id}/ - обновление публикации по id

Пример запроса:

{
"text": "string",
"image": "string",
"group": 0
}

PATCH /api/v1/posts/{id}/ - частичное обновление публикации по id 

Пример запроса:

{
"text": "string",
"image": "string",
"group": 0
}

DELETE /api/v1/posts/{id}/ - удаление публикации по id, удалить публикацию может только автор публикации

Пример запроса:

{
"id": 0
}

GET /api/v1/follow/ - показать подписки пользователя, сделавшего запрос

POST /api/v1/follow/ - подписаться на пользователя

Пример запроса:

{
"following": "username"
}