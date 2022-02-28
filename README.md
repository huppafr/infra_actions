# infra_actions
Учебный проект для изучения работы GitHub Actions. 
В данном проекте был разработан workflow, который реализует:
1. Проверку кода на соответствие PEP8 и прогоняет его через pytest
2. Загружает обновленные образы в Dockerhub
3. Деплоит код на продуктивный сервер
4. Отправляет уведомление об одачном завершении workflow

## Технологии
- Python 3.9
- Django 4.0.2
- gunicorn 20.0.4
- Nginx 1.18
- Docker 20.10.6
- PostgreSQL 12.4

## Установка:

1. Клонируйте репозиторий на локальный компьютер
2. Создайте и активируйте виртуальное окружение
```bash
python3 -m venv venv
. venv/bin/activate
```
3. Установите зависимости
```bash
pip install -r requirements.txt
```


## Подготовка инфраструктуры:

### Запуск сайта локально из директории backend/
``` python manage.py runserver ```
### Запуск сервера из ubuntu осуществляется командой
``` docker-compose up ```
### команда для удаления базы данных и всех volumes
``` docker-compose down -v```
### команда для создания суперпользователя, работает только с запущенным контейнером
``` docker-compose exec backend python manage.py createsuperuser ```
### Команда для заполнения ингредиентами
``` docker-compose exec backend python manage.py loaddata fixtures/ingredients.json ```
### команда для заполнения проекта статикой
``` docker-compose exec backend python manage.py collectstatic ```

## Автор
- Хюппенен Артём

