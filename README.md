### Описание:

Данный проект представляет собой некое подобие социальной сети. 
Функционал дорстаточно обширный, а именно:
- Просмотр постов различных авторов
- Создание, редактирование, удаление собственных постов
- Подписка на определённых авторов
- Комментирование постов
Все возможности доступны только при аутентификации.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/illager10/api_final_yatube.git
```

```
cd yatube_api
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```

### Примеры запросов к API:

GET http://127.0.0.1:8000/api/v1/posts/

```
{
    "count": 123,
    "next": "http://api.example.org/accounts/?offset=400&limit=100",
    "previous": "http://api.example.org/accounts/?offset=200&limit=100",
    "results": [
        {
            "id": 0,
            "author": "string",
            "text": "string",
            "pub_date": "2021-10-14T20:41:29.648Z",
            "image": "string",
            "group": 0
        }
    ]
}
```

GET http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/

```
[
    {
        "id": 0,
        "author": "string",
        "text": "string",
        "created": "2019-08-24T14:15:22Z",
        "post": 0
    }
]
```

GET http://127.0.0.1:8000/api/v1/groups/

```
[
    {
        "id": 0,
        "title": "string",
        "slug": "string",
        "description": "string"
    }
]
```

GET http://127.0.0.1:8000/api/v1/follow/

```
[
    {
    "user": "string",
    "following": "string"
    }
]
```