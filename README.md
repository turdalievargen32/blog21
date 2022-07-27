# Django project blog 
# commands
> `django-admin startproject config` - создает проект, если поставить . то проект создается в этой же папке, если не поставить, то создаться папка config и в ней создается проект 
> `python manage.py startapp app_name` - создает приложение 
> `python manage.py makemigrations` - проверяет models, если есть изменения, то создает новый файл в migrations с изменниями 
> `python manage.py migrate` - считывает все файлы миграций  и выполняет в бд (изменяет строение таблиц)
> `python manage.py runserver` - запускает наш проект на 127.0.0.1:8000
> `python manage.py runserver 5000` -  запускает наш проект на 127.0.0.1:5000




## setting.py 
* BASE_DIR - корневая папка нашего проекта 
* SECRET_KEY - секретный ключ проекта
* DEBUG - настройка, которая если True, все ошибки будут отоброжаться, поэтому production мы ставим его False
* ALLOWED_HOSTS -  хосты, на которых размещен запуск нашего проекта( если список пустой - можно запустить на localhost(127.0.0.1))
* INSTALLED_APPS - все приложения которые будут использовать наш проект 
* MIDDLEWARE - все middleware (функции, которые обробатывает запрос), которые будут использовать наш проект 
* ROOT_URLCONF - главный файл urls 
* DATABASES - настроки базы даннных, которые будет использовать наш проект  

## как проходит запрос 
1. wsgi/asgi (те, кто принимает запрос и возвращает ответ )
2. settings -> gmiddlewares (функции которе обробатывают запрос)
3. urls (маршрутизатор которыцй проворяет часть url и если находит совподение передает запрос  нужной функции (views))
4. views (функции которые "понимают' запрос и возвращает даннные в нужном формате)
5. serializers (классы которые преоброзуют данные из json в обьекты от модельки и наоборот )
6. models (классы которые обозночают как будет выглядит наша таблица и столбцы там есть )
7. managers (objects)    (классы, которые работают с ORM, у них есть методы для создания, обновления, удаления, получения, фильтрации записей из таблиц )
8. db (база данных)

