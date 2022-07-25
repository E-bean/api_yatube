## api_final_yatube:

### Описание:

API для проектра социальная сеть Yatube.

Доступ к чтению публикаций есть у любого пользователя.

Для авторизированных пользователей доступны добавления и изменения публикаций,
добавления комментариев и подписка на авторов.

Аутентификация осуществляется по JWT-токену.


### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/E-bean/api_final_yatube
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

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


### Примеры:

Получение публикации.

GET /api/v1/posts/5/

```
{
  "id": 5,
  "author": "Tatiana",
  "text": "Сегодня солнечно!",
  "pub_date": "2022-04-26T14:15:22Z",
  "group": 0
}
```

Обновление комментария к публикации по id. Обновить комментарий может только автор комментария. Анонимные запросы запрещены.

PUT /api/v1/posts/5/comments/1/

```
{
    "text": "Ура!"
}
```

POST /api/v1/jwt/create/
```
{
"username": "string",
"password": "string"
}
```
