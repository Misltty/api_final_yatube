Проект «API для Yatube»

Описание проекта

В проекте реализован интерфейс API, который позволяет социальной сети "Yatube" взаимодействовать с другой программой.

Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

git clone https://github.com/misltty/api_final_yatube.git
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

Примеры запросов API

Получение публикации по id(GET): http://127.0.0.1:8000/api/v1/posts/{id}/
{post_id} - id публикации
Допустимы анонимные запросы от пользователей


Добавление нового комментария к публикации.(POST): http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/
{post_id} - id публикации
Анонимные запросы запрещены.

# Тело запроса

    {
        "text": "string",
    }

Обновление комментария к публикации по id(PUT): http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{id}/
{post_id} - id публикации
{id} - id комментария
Обновить комментарий может только автор комментария.
Анонимные запросы запрещены.

# Тело запроса

    {
        "text": "string",
    }


Частичное обновление публикации по id(PATCH): http://127.0.0.1:8000/api/v1/posts/{id}/
{id} - id публикации
Обновить публикацию может только автор публикации. 
Анонимные запросы запрещены.

# Тело запроса

    {
       "text": "string",
       "image": "string",
       "group": 0
    }

Автор - Семенова Мария
Git-профиль: https://github.com/Misltty 
