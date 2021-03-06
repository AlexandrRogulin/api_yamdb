Проект YaMDb собирает через API отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка».
Пользователи могут писать отзывы и оставлять оценки к произведениям, а также комментировать отзывы других пользователей.
запросы к API начинаются с /api/v1/

Доступные сущности
Пользователи
Категории
Жанры
Рейтинги
Отзывы
Комментарии

Подготовка рабочей среды
Перейдите в свою рабочую директорию и выполните следующие команды:

git clone https://github.com/AlexandrRogulin/api_final_yatube.git
cd api_final_yatube
Создайте и активируйте виртуальное окружение:

source -m venv venv

source venv/Scripts/activate

Установите необходимые зависимости:

pip install -r requirements.txt

Выполните миграции:

python manage.py migrate

Активируйте сервер:

python manage.py runserver

Доступные методы:

/api/v1/posts (GET, POST, PUT, PATCH, DELETE)

/api/v1/posts/<id> (GET, POST, PUT, PATCH, DELETE)
    
/api/v1/posts/<id>/comments (GET, POST, PUT, PATCH, DELETE)
    
/api/v1/posts/<id>/comments/<id> (GET, POST, PUT, PATCH, DELETE)
    
/api/v1//group/ (GET< POST)

/api/v1/follow/ (GET, POST)
                           
Пример запроса к API:
import requests

api = 'http://127.0.0.1/api/v1/posts/'
data = {
    'text': 'New post',
}
headers = {'Authorization': 'Bearer your_token'}
r = requests.post(api, data=data, headers=headers)
