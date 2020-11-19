# bakend-django-tdd

some commands used in the project
```bash
docker build .
docker-compose build
docker-compose run app sh -c "django-admin.py startproject app ."
docker-compose run app sh -c "python manage.py test"
docker-compose run app sh -c "python manage.py test && flake8"
docker-compose run app sh -c "python manage.py startapp core"
docker-compose run app sh -c "python manage.py makemigrations core"
docker-compose up
docker-compose run app sh -c "python manage.py createsuperuser"
```

to test in browser
[admin console](http://127.0.0.1:8000/admin/)
[home url](http://127.0.0.1:8000)
