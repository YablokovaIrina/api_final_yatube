API для проекта Yatube
Yatube - социальная сеть для блогеров. Неутентифицированным пользователям API доступен только на чтение. Исключение - эндпоинт /follow/: доступ к нему предоставляется только аутентифицированным пользователям. В проекте использована аутентификация по JWT-токенам. Аутентифицированным пользователям разрешено изменение и удаление своего контента. Добавление новых пользователей через API не осуществляется.

Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:

git clone https://github.com/YablokovaIrina/api_final_yatube.git
cd api_final_yatube
Cоздать и активировать виртуальное окружение:

python3 -m venv env
source env/bin/activate
Установить зависимости из файла requirements.txt:

python3 -m pip install --upgrade pip
pip install -r requirements.txt
Выполнить миграции:

python3 manage.py migrate
Запустить проект:

python3 manage.py runserver
Примеры некоторых запросов к API:
GET http://127.0.0.1:8000/api/v1/posts/
Вернёт:

{
    "count": 123,
    "next": "http://api.example.org/accounts/?offset=400&limit=100",
    "previous": "http://api.example.org/accounts/?offset=200&limit=100",
    "results":[
        +{...}
    ]
}
POST http://127.0.0.1:8000/api/v1/follow/
{
    "following": "string"
}
Вернёт:

{
    "user": "string",
    "following": "string"
}

Об авторе:
Ирина Яблокова