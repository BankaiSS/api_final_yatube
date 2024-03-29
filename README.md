# api_final

### Описание:

API_FINAL_YATUBE - это REST API для социальной сети Yatube. В проекте реализованы возможность просмотривать, создавать, обновлять и удалять посты, просмотривать группы(сообщества), коментировать посты, а также подписываться на авторов постов.
Авторизация на сайте: регистрация, получение, обновление и проверка JWT.

#### Технологии использованные в проекте:

* Python
* Django
* DRF
* Simple JWT

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone 'ссылка на репу'
```

```
cd kittygram_backend
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```
### Примеры запросов к API:

## Запрос JWT токена с использованием логина и пароля пользователя User123:
```
  [POST].../api/v1/jwt/create/
  {
    "username": "User123",
    "password": "15963fdg"
}
```
### Ответ:
```
{"refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTY1MjA5NTYwNywianRpIjoiMDBmMGI0MG.sE5Bd3vrnQLIAL5GxxFg36tPoYyB9I5MQBE_iGshpK4",
    "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNjUyMDk1NjA3LCJqdGkiOiI0YmIxN2MzODcwNGU0YzQ0OWQ4Nzg4NzA4ODcyZTliMCIsInVzZXJfaWQiOjF9"
}
```
### Запрос с использованием токена пользователя User123 для публикации поста:
```
    [POST].../api/v1/posts/
    {
    "text": "Hello, ladies.",
    "group": 1   
    }
```

### Ответ:
```
{
    "id": 1,
    "text": "Hello, ladies.",
    "author": "SneakyBeaky",
    "image": null,
    "group": 1,
    "pub_date": "2023-02-13T22:48:48.782688Z"
}
```
### Запрос для просмотра групп анонимным пользователем:
```
    [GET].../api/v1/groups/
```
### Пример ответа:
```
    [
    {
        "id": 1,
        "title": "Group 1 for smth",
        "slug": "groupone",
        "description": "Group for something"
    },
    {
        "id": 2,
        "title": "Games",
        "slug": "Games Lovers",
        "description": "posts about computer games"
    }
]
```

### Подробная документация в формате ReDoc доступна по адресу .../redoc/

### Автор проекта:

Bankai