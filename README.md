# bakend-django-tdd

some commands used in the project
```bash
docker build .
docker-compose build
docker-compose run app sh -c "django-admin.py startproject app ."
docker-compose run app sh -c "python manage.py test && flake8"
docker-compose run app sh -c "python manage.py startapp core"
```