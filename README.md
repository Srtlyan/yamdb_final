[![CI](https://github.com/Srtlyan/yamdb_final/actions/workflows/yamdb_workflow.yaml/badge.svg)](https://github.com/Srtlyan/yamdb_final/actions/workflows/yamdb_workflow.yaml)

# Приложение YaMDb c REST API
* Приложение YaMDb хранит информацию о произведениях разных:
\- категорий (Например:Фильмы, Музыка, Книги)
\- жанров (Например: Рок, Фантастика, Детективы)
* Приложение YaMDb хранит отзывы пользователей на произведения и оценки, которые пользователи ставят произведениям. 

## Запуск приложения


1. Разверните контейнеры:
`docker-compose up`
2. Проверьте запущенные контейнеры:
`docker container ls`
3. Скопируйте занчение CONTAINER ID контейнера web
4. Проведите последовательно миграции внутри контейнера web:
`docker exec -it <container id> python manage.py migrate auth`
`docker exec -it <container id> python manage.py makemigrations api`
`docker exec -it <container id> python manage.py migrate api`
`docker exec -it <container id> python manage.py migrate`
5. Создайте суперпользователя:
`docker exec -it <container id> python manage.py createsuperuser` 
6. Заполните базу данными из файла *fixtures.json*:
 `docker exec -it <container id> python loaddata fixtures.json`

 ## Проект доступен по адресу: 
http://178.154.213.229/admin/login/